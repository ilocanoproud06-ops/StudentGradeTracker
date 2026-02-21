# Plan: Auto-Sync GitHub Pages + Firebase & Navigation URLs

## Information Gathered:
- GitHub Pages URL: https://ilocanoproud06-ops.github.io/StudentGradeTracker/
- Firebase configured at: studentgradetracker-e04c0.firebaseapp.com
- Admin portal: admin_portal.html - exports data.json manually
- Student portal: student.html - auto-detects GitHub Pages URL
- SyncManager already handles Firebase sync and localStorage fallback

## Problem:
1. GitHub Pages is static hosting - cannot write directly from browser
2. Currently requires manual export of data.json for student access
3. No automatic sync to GitHub Pages URL
4. Navigation URLs not displayed to users

## Plan:

### Phase 1: Update firebase-config.js
1. Add function to get all navigation URLs (GitHub Pages, Firebase, Local)
2. Add GitHub API integration for auto-update of data.json
3. Add better status tracking for all sync sources
4. Add URL display helper functions

### Phase 2: Update admin_portal.html
1. Add URL display section in sidebar showing:
   - GitHub Pages URL (live)
   - Firebase URL reference
   - Local file path
2. Add "Copy URL" buttons for easy sharing
3. Add auto-sync indicator and settings

### Phase 3: Update student.html
1. Add URL display showing current data source
2. Show all available access URLs on login screen
3. Add refresh indicator showing data source

### Phase 4: GitHub API Integration (Optional)
- Use GitHub REST API to update data.json
- Requires Personal Access Token (stored securely)
- Auto-commit on data changes

## Files to Edit:
- firebase-config.js (add URL functions, GitHub API)
- admin_portal.html (add URL display in sidebar)
- student.html (add URL display on login)

## Followup Steps:
- Test Firebase sync
- Configure GitHub API token (optional)
- Deploy updates to GitHub Pages

