# Not Just Black - Chrome Theme

# Description

A sleek, minimalist dark theme for Chrome featuring pure black backgrounds and crisp white text. "Not Just Black" provides maximum contrast for comfortable browsing while maintaining a clean, professional appearance.

# Features
- **Pure black window frames and backgrounds** for a truly dark experience
- **High-contrast white text** for excellent readability
- **Custom New Tab Page background** with centered image
- **Optimized for both regular and incognito modes**
- **Clean, distraction-free design** that's easy on the eyes

# Preview
The theme includes:
- Black browser frame and toolbar backgrounds
- Dark gray (#222222) toolbar for subtle contrast
- White text on all tabs (active, inactive, and incognito)
- Black New Tab Page with custom background image
- White address bar text on dark background

# Customization

To modify the theme:

**Any Text Editor:**
1. **Colors**: Edit the `colors` section in `not-just-black/manifest.json`
2. **Background**: Replace `not-just-black/img/theme_ntp_background.png` with your image
3. **Icon**: Update files in `not-just-black/icon/` directory
4. **Properties**: Adjust `properties` in manifest for background positioning

**Git Bash (Windows) / Terminal (Mac/Linux):**
```
# After making changes, rebuild
make package
```

# Installation

### From Chrome Web Store (Recommended)
1. Visit the Chrome Web Store (link coming soon)
2. Click "Add to Chrome"
3. Enjoy your new dark theme!

### Developer Installation (For Testing)
**Git Bash (Windows) / Terminal (Mac/Linux):**
```
# Navigate to project directory
cd /path/to/customChromeTheme

# Verify project structure
make verify
```

**Any OS - Chrome Browser:**
1. Download or clone this repository
2. Open Chrome and go to `chrome://extensions/`
3. Enable "Developer mode" in the top right
4. Click "Load unpacked"
5. Select the `not-just-black` folder (not the root project folder)
6. The theme will be applied automatically

### Built Package Installation
**Git Bash (Windows) / Terminal (Mac/Linux):**
```
# Build the CRX file
make package
```

**Any OS - Chrome Browser:**
1. Find `built/not-just-black.crx` in the built directory
2. Open Chrome and go to `chrome://extensions/`
3. Enable "Developer mode"
4. Drag and drop the CRX file from `built/` onto the extensions page

### Build Directory Structure
After running `make package`, your `built/` directory will contain:
```
built/
├── not-just-black.crx    # Direct installation file
└── not-just-black.zip    # Chrome Web Store upload file
```

## Development

### Prerequisites
- **Windows**: 
  - Make installed ([installation guide](https://gnuwin32.sourceforge.net/packages/make.htm))
  - **Git for Windows** (includes OpenSSL and Git Bash) - **Recommended**
  - OpenSSL for key generation
- **Mac/Linux**: Make and OpenSSL usually pre-installed

### Terminal/Shell Requirements

**Windows Users - Recommended Setup:**
- Use **Git Bash** for all `make` commands (comes with Git for Windows)
- Git Bash provides Unix-like environment with proper make/OpenSSL support
- PowerShell can be used for file operations but may have compatibility issues with make

**Alternative Windows Options:**
- **PowerShell**: Limited compatibility, may require workarounds
- **Command Prompt (cmd)**: Not recommended, lacks proper Unix tool support
- **WSL (Windows Subsystem for Linux)**: Full compatibility, but requires setup

**Mac/Linux Users:**
- Use **Terminal** with bash/zsh (default)

### Build Commands

**Git Bash (Windows) / Terminal (Mac/Linux):**
```
# Create ZIP package for Chrome Web Store (output: built/)
make zip

# Build signed CRX file (output: built/)
make build

# Create both ZIP and CRX files in built/ directory
make package

# Generate new signing key
make new-key

# Clean up ALL generated files (including built/ directory)
make clean

# Show developer installation instructions
make install-dev

# Verify project structure and dependencies
make verify

# Show all available commands and configuration
make help
```

### Build Output
All build artifacts are automatically organized in the `built/` directory:
- `built/not-just-black.zip` - For Chrome Web Store upload
- `built/not-just-black.crx` - For direct installation/testing

The Makefile automatically creates the `built/` directory and moves all output files there to keep your project root clean and organized.

### Project Structure

```
customChromeTheme/
├── .dist/                     # Distribution files (optional)
├── built/                     # Build output directory
│   ├── not-just-black.crx     # Signed extension file
│   └── not-just-black.zip     # Chrome Web Store package
├── makefiles/                 # Build configuration
│   ├── general_makefile       # Generic reusable Makefile
│   └── Makefile.backup        # Backup of original Makefile
├── not-just-black/            # Theme source directory
│   ├── icon/                  # Extension icons
│   │   ├── icon               # Generic icon file
│   │   ├── icon.png           # 128x128 PNG icon
│   │   └── icon.svg           # Vector icon source
│   ├── img/                   # Theme assets
│   │   └── theme_ntp_background.png  # New Tab Page background
│   └── manifest.json          # Theme configuration
├── img-dump/                  # Screenshots and promotional images
│   ├── Chrome Theme Small Tile.jpg      # 440x280 promotional tile
│   ├── Screenshot 2025-09-21 000621.png # Browser screenshot
│   ├── Screenshot 2025-09-21 001407.png # Theme in action
│   └── screenshot.jpg         # Additional screenshots
├── .gitignore                 # Git ignore rules
├── crxmake.sh                 # CRX packaging script
├── key.pem                    # Private signing key (keep secure!)
├── Makefile                   # Build automation
└── README.md                  # This documentation
```

## Assets and Media

### Icons
- **Vector source**: `not-just-black/icon/icon.svg` (editable)
- **PNG format**: `not-just-black/icon/icon.png` (128x128px)
- **Generic**: `not-just-black/icon/icon` (fallback)

### Screenshots and Promotional Images
Located in `img-dump/` directory:
- **Small promotional tile**: `Chrome Theme Small Tile.jpg` (440x280px)
- **Browser screenshots**: Various PNG files showing theme in action
- **Additional media**: `screenshot.jpg` and timestamped captures

### Theme Assets
- **New Tab background**: `not-just-black/img/theme_ntp_background.png`

#### Color Reference
```
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

**Any Text Editor:**
1. Update the version number in `not-just-black/manifest.json`

**Git Bash (Windows) / Terminal (Mac/Linux):**
```
# Create fresh builds
make package
```

**Chrome Web Store Dashboard:**
2. Upload `built/not-just-black.zip` to Chrome Web Store Developer Dashboard
3. Submit for review

## Troubleshooting

### Windows Users
- **Make command not found**: Install Git for Windows and use Git Bash
- **OpenSSL errors**: Ensure Git for Windows is installed (includes OpenSSL)
- **PowerShell issues**: Switch to Git Bash for better compatibility

### All Platforms
- **Missing files**: Run `make verify` to check project structure
- **Build failures**: Check that all prerequisites are installed
- **Permission errors**: Ensure you have write access to project directory

## Security Notes

- **Private key**: `key.pem` should never be committed to version control
- **Gitignore**: Already configured to exclude sensitive files (`*.pem`, `built/`)
- **Backup**: Keep `key.pem` securely backed up for future updates
- **Clean builds**: Use `make clean` to remove all generated files including `built/` directory

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