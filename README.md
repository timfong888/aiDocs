# Submodule Usage Guide

This repo is designed to be used as a Git submodule across multiple projects.

## Current Integrations
- **remoteObsidian1025**: Integrated as context for AI agents and documentation workflows

## Adding to New Project

```bash
# In your submodule folder
git submodule add https://github.com/timfong888/aiDocs
```

## Working with the Submodule
### Make changes in submodule
```bash
cd aiDocs
# edit files
git add .
git commit -m "Your changes"
git push origin main
```

# Update parent repo reference
```bash
cd ..
git add folder-name
git commit -m "Update submodule reference"
git push
```

# Update the local repo with the latest remote submodule repo
```bash
git submodule update --remote --recursive
```

## Team Setup

```bash
# After cloning parent repo
git submodule update --init --recursive
```

## Getting Updates from Other Projects

```bash
# Pull latest changes
cd folder-name
git pull origin main
cd ..
git add folder-name
git commit -m "Update to latest submodule"
```

## Pin to Specific Version (Optional)

```bash
cd folder-name
git checkout v1.2.3  # or commit hash
cd ..
git add folder-name
git commit -m "Pin to stable version"
```
