# GRIZCAM GPS Capture (PWA)

Progressive Web App for capturing GPS location and sending coordinates to GRIZCAM cameras.

## 🎉 Now Installable as an App!

This page can be installed on your phone like a native app - no app store needed!

**Live URL:** https://cwgold.github.io/gps-for-esp32/

## Features

✅ **Progressive Web App** - Install to home screen
✅ **Standalone Mode** - Opens without browser UI
✅ **Offline Capable** - Works without internet connection
✅ **Auto-redirect** - Returns to camera with coordinates
✅ **High Accuracy GPS** - Uses device GPS with high precision

## How to Install

### Android (Chrome/Edge)
1. Visit https://cwgold.github.io/gps-for-esp32/
2. Look for "Install app" banner at top
3. Tap "📲 Install App"
4. Icon appears on home screen

### iOS (Safari)
1. Visit https://cwgold.github.io/gps-for-esp32/
2. Tap **Share** button (bottom center)
3. Scroll and tap **"Add to Home Screen"**
4. Tap **"Add"**
5. Icon appears on home screen

## How to Use

### After Installation:
1. Tap **GRIZCAM GPS** icon on home screen
2. Tap **"📍 Capture GPS Location"**
3. Allow location permission when prompted
4. GPS captured → Auto-redirects to camera (192.168.4.1)
5. Coordinates are pre-filled in configuration

## Complete Setup Workflow

### First Time (Camera Setup):
1. Power on camera
2. Connect phone to **GRIZCAM_SETUP** WiFi
3. Captive portal appears (or manually go to 192.168.4.1)
4. See 4-step instructions with QR code
5. **Disconnect from WiFi** (Important!)
6. Scan QR code or visit https://cwgold.github.io/gps-for-esp32/
7. **Install the app** (one-time)
8. Capture GPS location
9. **Reconnect to GRIZCAM_SETUP WiFi**
10. Browser auto-redirects with coordinates
11. Save camera configuration

### Every Time After:
1. Connect to GRIZCAM_SETUP WiFi
2. Tap GRIZCAM GPS app icon
3. Capture location
4. Done! ✓

## Technical Details

- **Framework:** Vanilla JavaScript (no dependencies)
- **API:** HTML5 Geolocation API
- **Service Worker:** Caches app for offline use
- **Manifest:** PWA configuration for installation
- **Target Device:** ESP32-S3 camera at 192.168.4.1

## Why PWA?

**Traditional approach:**
- Open browser → type URL → bookmark it → find bookmark next time
- Or scan QR code each time

**PWA approach:**
- Install once → tap icon anytime
- Faster, cleaner, feels like native app
- No app store approval needed
- Works offline
- Auto-updates when online

## Requirements

- Modern browser (Chrome, Safari, Edge, Firefox)
- Device with GPS capability
- Location permission granted
- HTTPS (automatically provided by GitHub Pages)

## Files

- `index.html` - Main app interface
- `manifest.json` - PWA configuration
- `service-worker.js` - Offline caching
- `icon-192.png` - App icon (192x192)
- `icon-512.png` - App icon (512x512)

## Icon Status

⚠️ **Icons needed!** The app works but needs custom icons for a polished look.

### Quick Icon Creation:
1. Visit https://realfavicongenerator.net/
2. Upload a location pin image
3. Download generated icons
4. Rename to `icon-192.png` and `icon-512.png`
5. Upload to this repository

Or use the included `generate-icons.html` tool (open in browser, click download buttons).

## Development

To test locally:
```bash
# Serve with any HTTP server (HTTPS required for PWA features)
python3 -m http.server 8000
# Visit http://localhost:8000
```

Note: Full PWA features (installation, service worker) require HTTPS.

## Browser Compatibility

| Browser | Installation | GPS | Offline |
|---------|-------------|-----|---------|
| Chrome (Android) | ✅ | ✅ | ✅ |
| Safari (iOS) | ✅ | ✅ | ✅ |
| Edge (Android) | ✅ | ✅ | ✅ |
| Firefox (Android) | ⚠️ | ✅ | ✅ |

⚠️ Firefox supports PWA but installation is less prominent

## Troubleshooting

**Install prompt doesn't appear:**
- Wait a few seconds after page loads
- Check browser menu → "Install app" or "Add to home screen"
- Ensure you're on HTTPS (GitHub Pages provides this)

**GPS permission denied:**
- Settings → App Permissions → GRIZCAM GPS → Location → Allow
- Or try in regular browser first to grant permission

**Offline doesn't work:**
- Visit the page while online first (service worker needs to install)
- Check browser console for service worker errors

## License

MIT License - Free to use and modify

## Contributing

Issues and pull requests welcome!

## Related

- Main project: BlackMomba_v9_gen4 ESP32-S3 camera system
- Hardware: ESP32-S3 DevKit C-1 with thermal imaging
- Communication: ESP-NOW mesh network
