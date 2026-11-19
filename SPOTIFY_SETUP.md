# 🎵 Spotify Setup Guide - MMM-NowPlayingOnSpotify

## Step 1: Create a Spotify Developer App

1. Go to **https://developer.spotify.com/dashboard**
2. Log in with your Spotify account (or create one)
3. Click **Create an App**
4. Accept the terms and create the app
5. You'll see your app dashboard

## Step 2: Get Your Credentials

On your app dashboard, you'll find:
- **Client ID** - Copy this
- **Client Secret** - Copy this (keep this private!)

## Step 3: Set Up Redirect URI

1. Click **Edit Settings**
2. Under **Redirect URIs**, add:
   ```
   https://raywo.github.io/MMM-NowPlayingOnSpotify/callback/
   ```
3. Click **Add** then **Save**

## Step 4: Update Your config.js

Replace in your `config/config.js`:
```javascript
clientID: "YOUR_SPOTIFY_CLIENT_ID",        // Replace with your Client ID
clientSecret: "YOUR_SPOTIFY_CLIENT_SECRET", // Replace with your Client Secret
redirectUri: "https://raywo.github.io/MMM-NowPlayingOnSpotify/callback/",
```

## Step 5: First Time Authorization

1. Start MagicMirror
2. The mirror will show a **QR code**
3. **Scan it with your phone** (must be on same network)
4. Click authorize on your phone
5. Done! The module will show your now playing song

## What You'll See

✅ Album artwork (large cover)  
✅ Song title and artist  
✅ Album name  
✅ Progress bar with time elapsed and total time  
✅ Current playing device  

## Notes

- **Re-authorization:** Every 6 months, you'll need to rescan the QR code
- **Tokens stored:** in `modules/MMM-NowPlayingOnSpotify/tokens.json`
- **Multiple accounts:** You can authorize up to 5 Spotify accounts per app
- **Spotify Premium required:** Yes, you have this ✅

---

## Troubleshooting

**QR code not showing?**
- Check browser console for errors
- Make sure port 8080 is accessible

**Song not updating?**
- Verify Spotify is playing on a device
- Check that the authorized device is the same as where you're playing

**"Cannot read tokens"**
- Delete `modules/MMM-NowPlayingOnSpotify/tokens.json`
- Restart and re-authorize with QR code
