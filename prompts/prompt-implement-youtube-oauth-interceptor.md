# Implement YouTube OAuth Interceptor - Remote Agent Prompt

## 🎯 **Objective**
Implement the YouTube OAuth interceptor for automatic token management in FlutterFlow, following the preserved design documentation and FlutterFlow best practices.

## 📋 **Context & Prerequisites**

### **Current State**
- ✅ FlutterFlow has created placeholder `youtubeOauthInterceptor` class in `lib/custom_code/actions/youtube_oauth_interceptor.dart`
- ✅ Interceptor is exported in `lib/backend/api_requests/interceptors.dart`
- ✅ Base `FFApiInterceptor` infrastructure exists
- ✅ `GoogleOAuthCall` and OAuth infrastructure operational
- ❌ Custom functions for token management missing
- ❌ Interceptor implementation is placeholder only

### **Design Documentation Available**
- `docs/project/oauth-interceptor/RECOMMENDED_INTERCEPTOR_DESIGN.md` - Complete implementation code
- `docs/project/oauth-interceptor/GOOGLE_AUTH_SEQUENCE_DIAGRAM.md` - Flow documentation
- `docs/project/oauth-interceptor/YOUTUBE_API_INTERCEPTOR_GUIDE.md` - Integration guide
- `aiDocs/context/flutterflow-vsc.md` - FlutterFlow development procedures
- `aiDocs/context/API Calls _ FlutterFlow Documentation.md` - API interceptor guidelines

## 🚀 **Implementation Tasks**

### **Phase 1: Add Custom Functions to `lib/flutter_flow/custom_functions.dart`**

**Task 1.1: Add `getValidAccessToken()` Function**
```dart
/// Get a valid access token - handles validation and refresh
Future<String?> getValidAccessToken() async {
  try {
    final currentToken = FFAppState().tokensMap.accessToken;
    final currentExpiry = FFAppState().tokensMap.expiry;

    // Check if current token is still valid (5-minute grace period)
    if (currentToken.isNotEmpty && currentExpiry > 0) {
      final currentTime = DateTime.now().millisecondsSinceEpoch;
      const gracePeriod = 300000; // 5 minutes
      
      if (currentTime < (currentExpiry - gracePeriod)) {
        return currentToken; // Token is still valid
      }
    }

    // Token needs refresh
    final currentRefreshToken = FFAppState().tokensMap.refreshToken;
    
    final refreshResponse = await GoogleOAuthCall.call(
      userId: currentUserReference?.id,
      accessToken: currentToken.isNotEmpty ? currentToken : null,
      refreshToken: currentRefreshToken.isNotEmpty ? currentRefreshToken : null,
      expiryDate: currentExpiry > 0 ? currentExpiry : null,
    );

    if (refreshResponse.succeeded) {
      final newToken = GoogleOAuthCall.accessToken(refreshResponse.jsonBody);
      final newRefreshToken = GoogleOAuthCall.refreshToken(refreshResponse.jsonBody);
      final newExpiry = GoogleOAuthCall.expiryDate(refreshResponse.jsonBody);

      if (newToken != null && newToken.isNotEmpty) {
        FFAppState().updateTokensMapStruct(
          (e) => e
            ..accessToken = newToken
            ..refreshToken = newRefreshToken ?? currentRefreshToken
            ..expiry = newExpiry ?? 0,
        );
        return newToken;
      }
    }

    return null; // Refresh failed
  } catch (e) {
    return null; // Error occurred
  }
}
```

**Task 1.2: Add `isAuthError()` Function**
```dart
/// Simple check for authentication errors in API responses
bool isAuthError(dynamic response) {
  if (response == null) return false;
  
  try {
    if (response is Map<String, dynamic>) {
      final statusCode = response['statusCode'];
      final errorCode = response['error']?['code'];
      return statusCode == 401 || statusCode == 403 || 
             errorCode == 401 || errorCode == 403;
    }
  } catch (e) {
    // Ignore parsing errors
  }
  
  return false;
}
```

### **Phase 2: Implement Interceptor Class**

**Task 2.1: Update `lib/custom_code/actions/youtube_oauth_interceptor.dart`**

Replace the placeholder implementation with:

```dart
// Automatic FlutterFlow imports
import '/backend/backend.dart';
import '/backend/schema/structs/index.dart';
import '/backend/schema/enums/enums.dart';
import '/backend/supabase/supabase.dart';
import '/actions/actions.dart' as action_blocks;
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import 'index.dart'; // Imports other custom actions
import '/flutter_flow/custom_functions.dart'; // Imports custom functions
import 'package:flutter/material.dart';
// Begin custom action code
// DO NOT REMOVE OR MODIFY THE CODE ABOVE!

import '/backend/api_requests/api_interceptor.dart';

/// YouTube OAuth Interceptor - Automatic token management
class youtubeOauthInterceptor extends FFApiInterceptor {
  @override
  Future<ApiCallOptions> onRequest({
    required ApiCallOptions options,
  }) async {
    try {
      // Get valid access token (handles validation and refresh automatically)
      final token = await getValidAccessToken();
      
      if (token != null && token.isNotEmpty) {
        // Add Authorization header to the request
        final headers = Map<String, String>.from(options.headers);
        headers['Authorization'] = 'Bearer $token';
        
        // Return modified options with auth header
        return options.copyWith(headers: headers);
      }
    } catch (error) {
      // Don't break API flow on interceptor errors
      print('YouTube OAuth Interceptor onRequest error: $error');
    }
    
    return options;
  }

  @override
  Future<ApiCallResponse> onResponse({
    required ApiCallResponse response,
    required Future<ApiCallResponse> Function() retryFn,
  }) async {
    try {
      // Check if response indicates authentication error
      if (isAuthError(response.jsonBody)) {
        print('YouTube OAuth Interceptor: Auth error detected, attempting token refresh');
        
        // Try to refresh token once more
        final token = await getValidAccessToken();
        
        if (token != null && token.isNotEmpty) {
          print('YouTube OAuth Interceptor: Token refreshed successfully');
          // Token was refreshed, could retry the request in future enhancement
          return response;
        } else {
          print('YouTube OAuth Interceptor: Token refresh failed, user may need to re-authenticate');
        }
      }
    } catch (error) {
      // Don't break API flow on interceptor errors
      print('YouTube OAuth Interceptor onResponse error: $error');
    }
    
    return response;
  }
}
```

## 🔧 **FlutterFlow Integration Requirements**

### **Custom Functions Configuration**
After adding functions to `custom_functions.dart`, configure in FlutterFlow UI:

**`getValidAccessToken()`:**
- Return Type: `Future<String?>` (Future of nullable String)
- Parameters: None
- Description: "Get a valid access token, handles validation and refresh automatically"

**`isAuthError()`:**
- Return Type: `bool`
- Parameters: `response` (JSON, nullable)
- Description: "Check if API response indicates authentication error (401/403)"

### **Interceptor Application**
1. Navigate to API Calls > YouTube Data API group
2. Go to Advanced Group Settings
3. Add "youtubeOauthInterceptor" to group interceptors
4. Save group settings

## 📝 **Implementation Guidelines**

### **FlutterFlow Best Practices**
- Follow exact import structure from existing custom actions
- Maintain FlutterFlow's automatic import comments
- Use proper error handling that doesn't break API flows
- Include debug print statements for troubleshooting

### **OAuth Integration Points**
- Uses existing `GoogleOAuthCall` for token refresh
- Maintains `FFAppState().tokensMap` consistency
- Respects 5-minute grace period matching OAuth submodule
- Handles authUrl scenarios gracefully (falls back to existing flow)

### **Error Handling Strategy**
- Never throw exceptions that break API calls
- Log errors for debugging but continue execution
- Graceful degradation when token refresh fails
- Preserve original API response structure

## 🧪 **Testing Requirements**

### **Unit Testing**
1. Test `getValidAccessToken()` with valid tokens
2. Test `getValidAccessToken()` with expired tokens
3. Test `isAuthError()` with various response formats
4. Test interceptor class instantiation

### **Integration Testing**
1. Test with YouTube API calls (GET Playlists, GET Subscriptions)
2. Test token refresh scenarios
3. Test with expired/invalid tokens
4. Verify app state updates correctly

### **Validation Criteria**
- ✅ Custom functions compile and save in FlutterFlow
- ✅ Interceptor class compiles without errors
- ✅ YouTube API calls work without manual token management
- ✅ Token refresh happens automatically
- ✅ App state `tokensMap` updates correctly
- ✅ No breaking changes to existing functionality

## 📚 **Reference Documentation**
- Review `docs/project/oauth-interceptor/RECOMMENDED_INTERCEPTOR_DESIGN.md` for complete implementation details
- Check `docs/project/oauth-interceptor/GOOGLE_AUTH_SEQUENCE_DIAGRAM.md` for flow understanding
- Follow procedures in `aiDocs/context/flutterflow-vsc.md`
- Reference `aiDocs/context/API Calls _ FlutterFlow Documentation.md` for interceptor patterns

## 🎯 **Success Metrics**
- YouTube API calls work seamlessly without manual token management
- Token refresh happens automatically in background
- No authentication errors during normal usage
- Graceful handling of consent scenarios (authUrl flow)
- Zero breaking changes to existing app functionality

## 🚨 **Critical Notes**
- Do NOT modify the automatic FlutterFlow import structure
- Do NOT break existing API call functionality
- Do NOT remove error handling safeguards
- DO test thoroughly before marking complete
- DO follow the exact code structure from design docs
