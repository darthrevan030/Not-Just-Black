# Not Just Black - Chrome Theme

A sleek, minimalist dark theme for Chrome featuring pure black backgrounds and crisp white text. "Not Just Black" provides maximum contrast for comfortable browsing while maintaining a clean, professional appearance.

## Features

- **Pure black window frames and backgrounds** for a truly dark experience
- **High-contrast white text** for excellent readability
- **Custom New Tab Page background** with centered image
- **Optimized for both regular and incognito modes**
- **Clean, distraction-free design** that's easy on the eyes

## Preview

The theme includes:
- Black browser frame and toolbar backgrounds
- Dark gray (#222222) toolbar for subtle contrast
- White text on all tabs (active, inactive, and incognito)
- Black New Tab Page with custom background image
- White address bar text on dark background

## Installation

### From Chrome Web Store (Recommended)
1. Visit the Chrome Web Store (link coming soon)
2. Click "Add to Chrome"
3. Enjoy your new dark theme!

### Developer Installation (For Testing)
1. Download or clone this repository
2. Open Chrome and go to `chrome://extensions/`
3. Enable "Developer mode" in the top right
4. Click "Load unpacked"
5. Select the `not-just-black` folder
6. The theme will be applied automatically

## Development

### Prerequisites
- **Windows**: Make sure you have `make` installed ([installation guide](https://gnuwin32.sourceforge.net/packages/make.htm))
- **Mac/Linux**: Make is usually pre-installed
- **OpenSSL** for key generation (comes with Git for Windows)

### Build Commands

```bash
# Create ZIP package for Chrome Web Store
make zip

# Build signed CRX file
make

# Generate new signing key
make key.pem

# Clean up generated files
make clean

# Show developer installation instructions
make install-dev
```

### File Structure

```
not-just-black/
├── manifest.json              # Theme configuration
├── img/
│   └── theme_ntp_background.png  # New Tab Page background
├── Makefile                   # Build automation
├── crxmake.sh                 # CRX packaging script
└── README.md                  # This file
```

### Customization

To modify the theme:

1. **Colors**: Edit the `colors` section in `manifest.json`
2. **Background**: Replace `img/theme_ntp_background.png` with your image
3. **Properties**: Adjust `properties` in manifest for background positioning

#### Color Reference
```json
{
  "frame": [0, 0, 0],              // Window border - pure black
  "toolbar": [34, 34, 34],         // Main toolbar - dark gray
  "tab_text": [255, 255, 255],     // All text - white
  "ntp_background": [0, 0, 0],     // New tab background - black
  "omnibox_background": [34, 34, 34] // Address bar - dark gray
}
```

## Technical Details

- **Manifest Version**: 3 (latest Chrome extension format)
- **Theme Type**: Static theme with custom background
- **Compatibility**: Chrome 88+ (Manifest V3 requirement)
- **File Size**: Minimal footprint

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Test the theme locally
5. Commit your changes (`git commit -am 'Add improvement'`)
6. Push to the branch (`git push origin feature/improvement`)
7. Create a Pull Request

## Publishing Updates

To update the Chrome Web Store version:

1. Update the version number in `manifest.json`
2. Run `make zip` to create the package
3. Upload `not-just-black.zip` to Chrome Web Store Developer Dashboard
4. Submit for review

## License

This theme is open source and available under the [MIT License](LICENSE).

## Support

If you encounter any issues or have suggestions:
- Create an issue on GitHub
- Check Chrome's theme documentation for advanced customization
- Test in Chrome's developer mode before publishing

## Changelog

### Version 1.0
- Initial release
- Pure black theme with white text
- Custom New Tab Page background
- Manifest V3 compatibility

---

**Made with ❤️ for a better browsing experience**