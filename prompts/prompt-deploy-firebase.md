If you are working on a firebase function, you need to deploy it.

1. confirm you are in an environment with $FIREBASE_TOKEN
2. echo "Firebase token length: ${#FIREBASE_TOKEN}"
3. deploy: `firebase deploy --only functions --project "$PROJECT_ID" --token "$FIREBASE_TOKEN"
