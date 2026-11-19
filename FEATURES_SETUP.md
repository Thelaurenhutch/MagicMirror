# 🎵🛒 Complete Setup Guide - Spotify, Grocery List & Alexa

## Overview

Your MagicMirror now has three amazing features:

| Feature | Module | Position | What It Does |
|---------|--------|----------|-------------|
| 🎵 **Now Playing** | MMM-NowPlayingOnSpotify | Center | Shows current Spotify song + album art + progress bar |
| 📋 **Grocery List** | MMM-Todoist | Bottom Left | Displays your Todoist tasks, synced with phone & Alexa |
| 🗣️ **Alexa Voice** | Todoist Skill | Via Alexa Device | Add items to list by voice |

## Setup Order (Follow These Steps!)

### 1️⃣ Set Up Spotify First (Takes 5 minutes)

**Read:** `SPOTIFY_SETUP.md`

What you'll do:
1. Create Spotify Developer app
2. Get Client ID and Client Secret
3. Add redirect URI
4. Update config.js with credentials
5. Authorize by scanning QR code

**Result:** Your mirror shows what's playing on Spotify!

### 2️⃣ Set Up Todoist (Takes 5 minutes)

**Read:** `TODOIST_SETUP.md`

What you'll do:
1. Create free Todoist account
2. Create "Grocery List" project
3. Get API token
4. Update config.js with token
5. (Optional) Share with partner

**Result:** Grocery list appears on mirror!

### 3️⃣ Set Up Alexa (Takes 5 minutes)

**Read:** `ALEXA_SETUP.md`

What you'll do:
1. Enable Todoist skill in Alexa app
2. Sign in with your Todoist account
3. Test with voice commands
4. (Optional) Set up for partner's Alexa

**Result:** "Alexa, add milk" → appears on mirror!

## Installation Commands

### On Your Raspberry Pi (when deploying):

```bash
# 1. Go to modules directory
cd ~/MagicMirror/modules

# 2. Install Spotify module
git clone https://github.com/raywo/MMM-NowPlayingOnSpotify
cd MMM-NowPlayingOnSpotify
npm install
cd ..

# 3. Install Todoist module
git clone https://github.com/cbrooker/MMM-Todoist
cd MMM-Todoist
npm install
cd ../..

# 4. Done! Start MagicMirror
npm start
```

## Configuration Files

All your settings are in `config/config.js`:

```javascript
{
  module: "MMM-NowPlayingOnSpotify",
  position: "middle_center",
  config: {
    clientID: "YOUR_SPOTIFY_CLIENT_ID",
    clientSecret: "YOUR_SPOTIFY_CLIENT_SECRET",
    redirectUri: "https://raywo.github.io/MMM-NowPlayingOnSpotify/callback/",
    updateInterval: 1000,
    showCoverArt: true,
    coverSize: 200
  }
},
{
  module: "MMM-Todoist",
  position: "bottom_left",
  config: {
    accessToken: "YOUR_TODOIST_API_TOKEN",
    projects: ["Grocery List"]
  }
}
```

## Your Mirror Layout

```
┌─────────────────────────────────────────┐
│  🕐 Clock          ⛅ Weather           │
│                                         │
│            🎵 Now Playing 🎵             │  ← Spotify
│         [Album Art - 200x200]            │
│         Song: "Blinding Lights"          │
│         Artist: The Weeknd               │
│         ━━━━━━━━━━━━ 2:00 / 3:20        │
│                                         │
│  📋 Grocery List                        │
│  - Milk                                 │
│  - Eggs                                 │
│  - Bread                                │
│                                         │
│  You're such an awesome person! ✨      │
│                                         │
│         New York Times Feed             │
└─────────────────────────────────────────┘
```

## Credentials Reference

| Service | Credential | Where to Get |
|---------|-----------|--------------|
| **Spotify** | Client ID | developer.spotify.com/dashboard |
| **Spotify** | Client Secret | developer.spotify.com/dashboard |
| **Todoist** | API Token | todoist.com/app/settings/integrations/developer |

## First Run Checklist

- [ ] **Spotify module installed** and config has Client ID/Secret
- [ ] **Spotify QR code scanned** to authorize
- [ ] **Todoist module installed** and config has API token
- [ ] **Todoist "Grocery List" project created**
- [ ] **Added items to Todoist** to test
- [ ] **Alexa Todoist skill enabled** (optional)
- [ ] **Tested Alexa voice command** (optional)

## Sharing with Your Partner

### Calendar (Already Done! ✅)
- Shared iCloud calendar via CalDAV

### Grocery List (New!)
1. Share Todoist "Grocery List" project with partner's email
2. They accept the invite
3. Both can add/edit items from phone
4. Both Alexa devices can add items (if both have Todoist skill)

### Spotify
- Shows what's currently playing on your Spotify account
- If partner has own account, would need separate setup

## Troubleshooting Quick Reference

| Issue | Solution |
|-------|----------|
| Spotify not updating | Check if music is actually playing, verify Client ID/Secret |
| Todoist not showing | Verify API token, check project name matches exactly |
| Alexa can't add items | Reauthorize Todoist skill, check Todoist project name |
| Mirror won't start | Check config.js syntax, verify all modules are installed |
| Items not syncing | Wait 1-2 minutes, restart MagicMirror, check internet |

## Next Steps

1. **Follow the individual setup guides** in order:
   - SPOTIFY_SETUP.md
   - TODOIST_SETUP.md
   - ALEXA_SETUP.md

2. **Update your config.js** with credentials from each service

3. **Test everything** on your local machine (optional)

4. **Commit to GitHub:**
   ```bash
   git add config/config.js *.md
   git commit -m "Add Spotify, Todoist, and Alexa integration"
   git push
   ```

5. **Deploy to Raspberry Pi** using RASPBERRYPI_SETUP.md

---

## Need Help?

- **Spotify issues?** Check SPOTIFY_SETUP.md
- **Todoist issues?** Check TODOIST_SETUP.md  
- **Alexa issues?** Check ALEXA_SETUP.md
- **General questions?** Check RASPBERRYPI_SETUP.md

You've got this! 🚀
