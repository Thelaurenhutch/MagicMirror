# 🪞 MagicMirror Setup Guide - Raspberry Pi Deployment

## What's Been Configured

Your MagicMirror now includes:
- ✅ **12-hour time format**
- ✅ **Imperial units** (°F, miles)
- ✅ **Washington DC location** for weather
- ✅ **CalDAV integration** with your Apple iCloud calendar
- ✅ **US Holidays calendar**
- ✅ **Weather** (current + forecast)
- ✅ **News feed** (New York Times)

## Deploying to Raspberry Pi

### Prerequisites
- Raspberry Pi with Raspberry Pi OS installed
- Node.js (v22+) installed
- Git installed (comes by default on Raspberry Pi)

### Installation Steps

1. **Clone the repository:**
```bash
git clone https://github.com/Thelaurenhutch/MagicMirror
cd MagicMirror
```

2. **Install MagicMirror dependencies:**
```bash
npm run install-mm:dev
```

3. **Install MMM-CalDAV module:**
```bash
cd modules
git clone https://github.com/MMRIZE/MMM-CalDAV
cd MMM-CalDAV
npm install
cd ../..
```

4. **Set up the `.env` file for CalDAV:**
```bash
cp config/.env.example modules/MMM-CalDAV/.env
```

Then edit the file with your credentials:
```bash
nano modules/MMM-CalDAV/.env
```

The file should contain:
```
CALDAV_SERVICE_USERNAME=hutch
CALDAV_SERVICE_PASSWORD=100jews
ICLOUD_username=thelurn@icloud.com
ICLOUD_password=zdle-gobl-idpj-wfka
```

5. **Start MagicMirror:**
```bash
npm start
```

Or for development with auto-reload:
```bash
npm run start:dev
```

## Configuration Files

- **Main config:** `config/config.js`
- **CalDAV template:** `config/.env.example`
- **CalDAV secrets:** `modules/MMM-CalDAV/.env` (create this, don't commit!)

## Important Security Notes

⚠️ **Never commit** the actual `.env` file to GitHub - it contains your passwords!

The `.env.example` file is in the config folder as a template. When you deploy:
1. Copy `.env.example` to `modules/MMM-CalDAV/.env`
2. Update with your credentials
3. Add `.env` to `.gitignore`

## Troubleshooting

**Calendar not showing:**
- Check that MMM-CalDAV module loaded (check console/logs)
- Verify `.env` file exists in `modules/MMM-CalDAV/`
- Check credentials are correct

**Module not loading:**
- Run `npm install` in the MMM-CalDAV directory
- Check logs: `pm2 logs`

**Weather not showing:**
- Already configured for Washington DC
- Check internet connection

## Next Steps

- Customize the news feeds in `config/config.js`
- Add more calendar feeds if needed
- Adjust module positions to fit your display
- Set up PM2 for auto-startup on reboot

Happy mirroring! 🚀
