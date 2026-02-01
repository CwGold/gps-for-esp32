# GPS Capture for ESP32

Simple, secure GPS location capture page for ESP32 camera configuration.

## What it does

This page captures your device's GPS location over HTTPS (secure connection) and automatically redirects you back to your ESP32's configuration page with the coordinates pre-filled.

## How to use

1. Connect to your ESP32 WiFi access point (usually `192.168.4.1`)
2. Open the configuration page
3. In the Device tab, click "Get GPS Link"
4. This will open this page in a new tab
5. Click "Capture GPS Location" and allow location access
6. You'll be automatically redirected back to the ESP32 with your coordinates filled in

## Live Page

**https://cwgold.github.io/gps-for-esp32/**

## Why this exists

Modern browsers block geolocation requests over HTTP (insecure connections), even on local IP addresses like `192.168.4.1`. By capturing the location on a secure HTTPS page first, then passing the coordinates via URL parameters, we work around this security restriction while maintaining the 95% automation of the process.

## Technical Details

- Uses HTML5 Geolocation API with high accuracy mode
- Auto-redirects to `http://192.168.4.1/?lat=XX.XXXXXX&lon=YY.YYYYYY`
- ESP32 web interface auto-fills latitude/longitude from URL parameters
- No server-side code required - pure client-side JavaScript

## Compatibility

Works on all modern browsers that support:
- HTML5 Geolocation API
- URLSearchParams
- Secure contexts (HTTPS)

Tested on Chrome, Firefox, Safari, and Edge.

## License

MIT License - Free to use and modify
