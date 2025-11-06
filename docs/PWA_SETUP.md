# PWA Icon Setup

## Generating PNG Icons

You need to create PNG icons from the provided `icon.svg` file. You have several options:

### Option 1: Online Tools (Easiest)

1. Visit https://convertio.co/svg-png/ or https://cloudconvert.com/svg-to-png
2. Upload the `icon.svg` file
3. Convert to PNG at 512x512 pixels and save as `icon-512.png`
4. Convert to PNG at 192x192 pixels and save as `icon-192.png`
5. Place both PNG files in the `docs` folder

### Option 2: Using ImageMagick (Command Line)

If you have ImageMagick installed:

```bash
# Generate 512x512 icon
magick icon.svg -resize 512x512 icon-512.png

# Generate 192x192 icon
magick icon.svg -resize 192x192 icon-192.png
```

### Option 3: Using Inkscape (Command Line)

If you have Inkscape installed:

```bash
# Generate 512x512 icon
inkscape icon.svg --export-type=png --export-width=512 --export-filename=icon-512.png

# Generate 192x192 icon
inkscape icon.svg --export-type=png --export-width=192 --export-filename=icon-192.png
```

### Option 4: Using an Online PWA Asset Generator

1. Visit https://www.pwabuilder.com/imageGenerator
2. Upload the `icon.svg` or create your own icon
3. Download the generated assets
4. Copy the 192x192 and 512x512 PNG files to the `docs` folder

## Installing the Web App on Mobile

### iOS (Safari)

1. Open the website in Safari
2. Tap the Share button (square with arrow)
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add"

### Android (Chrome)

1. Open the website in Chrome
2. Tap the menu (three dots)
3. Tap "Add to Home screen" or "Install app"
4. Tap "Install"

## Requirements Met

✅ **manifest.json** - Defines app name, icons, theme colors, and display mode
✅ **Service Worker** - Enables offline functionality and app installation
✅ **HTTPS** - GitHub Pages provides HTTPS automatically
✅ **Icons** - 192x192 and 512x512 PNG icons (need to be generated)
✅ **Meta Tags** - Theme color, viewport, and Apple-specific tags
✅ **Responsive Design** - Already mobile-friendly with Tailwind CSS

## Testing PWA Locally

To test the PWA locally with HTTPS:

1. Install `http-server` globally:

   ```bash
   npm install -g http-server
   ```

2. Serve with SSL (generate self-signed cert):

   ```bash
   http-server docs -S -C cert.pem -K key.pem -p 8080
   ```

3. Or use Python:
   ```bash
   cd docs
   python -m http.server 8080
   ```

Note: For full PWA testing, deploy to GitHub Pages or another HTTPS server.
