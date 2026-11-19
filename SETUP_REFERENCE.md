# 📋 Quick Reference - Your MagicMirror Setup

## What's Configured

### Local (Windows) - For Testing
Everything is set up in `config/config.js`:
- ✅ 12-hour time format
- ✅ Imperial units (°F, miles)  
- ✅ Washington DC weather (38.88783438458993, -76.97814238639052)
- ✅ Calendar with Apple iCloud integration
- ✅ US Holidays
- ✅ News feed
- ✅ **🎵 Spotify Now Playing** (center screen)
- ✅ **📋 Todoist Grocery List** (bottom left)
- ✅ **🗣️ Alexa integration** (voice to add items)

### For Raspberry Pi - Important!

Before deploying, you MUST:

1. **For CalDAV (Apple Calendar):**
```bash
cp config/.env.example modules/MMM-CalDAV/.env
nano modules/MMM-CalDAV/.env
```

2. **For Spotify & Todoist:**
   - Get Spotify Client ID & Secret (see SPOTIFY_SETUP.md)
   - Get Todoist API Token (see TODOIST_SETUP.md)
   - Update config.js with these credentials

3. **For Alexa:**
   - Enable Todoist skill in Alexa app (see ALEXA_SETUP.md)

## Files Created/Modified

✅ `config/config.js` - Updated with Spotify & Todoist modules
✅ `config/.env.example` - Template for CalDAV credentials
✅ `RASPBERRYPI_SETUP.md` - Deployment guide
✅ `SETUP_REFERENCE.md` - This file
✅ `FEATURES_SETUP.md` - Master setup for new features
✅ `SPOTIFY_SETUP.md` - Spotify configuration guide
✅ `TODOIST_SETUP.md` - Todoist configuration guide
✅ `ALEXA_SETUP.md` - Alexa integration guide

## Setup Order for New Features

1. **Read:** `FEATURES_SETUP.md` (5 minute overview)
2. **Follow:** `SPOTIFY_SETUP.md` (5 minutes)
3. **Follow:** `TODOIST_SETUP.md` (5 minutes)
4. **Follow:** `ALEXA_SETUP.md` (5 minutes)

Total time: ~20 minutes

## Credentials Reference

| Service | Credential | Store In |
|---------|-----------|----------|
| Spotify | Client ID | config/config.js |
| Spotify | Client Secret | config/config.js |
| Todoist | API Token | config/config.js |
| iCloud | Email | modules/MMM-CalDAV/.env |
| iCloud | App Password | modules/MMM-CalDAV/.env |

## Module Installation Commands

```bash
# On Raspberry Pi in ~/MagicMirror/modules:

git clone https://github.com/raywo/MMM-NowPlayingOnSpotify
cd MMM-NowPlayingOnSpotify && npm install && cd ..

git clone https://github.com/cbrooker/MMM-Todoist
cd MMM-Todoist && npm install && cd ..

git clone https://github.com/MMRIZE/MMM-CalDAV
cd MMM-CalDAV && npm install && cd ../..
```

## Next Steps

1. **Set up each feature** (follow guides in order above)
2. **Update config.js** with API credentials
3. **Test locally** (optional on Windows)
4. **Commit to GitHub:**
```bash
git add config/config.js *.md
git commit -m "Add Spotify, Todoist, and Alexa"
git push
```

5. **Deploy to Raspberry Pi** (see RASPBERRYPI_SETUP.md)

---

## 📱 For Your Partner

They can:
- ✅ View shared calendar (CalDAV)
- ✅ Add/edit grocery list (Todoist phone app)
- ✅ Add items via Alexa ("Alexa, add milk to Grocery List")
- ✅ See list on mirror in real-time

Setup required on their side:
1. Accept calendar share invite
2. Download Todoist app
3. Accept Todoist project share
4. Enable Todoist skill on their Alexa (optional)

---

**All set!** 🚀 Your mirror is ready for deployment to Raspberry Pi.

