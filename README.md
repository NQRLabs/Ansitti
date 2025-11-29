# Ansitti

<img alt="Ansitti logo" src="./assets/images/logo.png" style="margin-left:auto; margin-right:auto; display:block; width:200px;"/>

**Create stunning ANSI art from images and text with a powerful layer-based editor**

Live demo: [https://nqrlabs.com/Ansitti/](https://nqrlabs.com/Ansitti/)

---

## Features

- ✨ **Layer-Based Editing** - Add multiple image and text layers, reorder, and composite them
- 🎨 **16-Color ANSI Palette** - Authentic ANSI color support with interactive color picker
- 🔤 **Dual Character Modes** - Block characters (░▒▓█) or ASCII characters (.:-+=*#%@)
- 🖼️ **Image-to-ANSI Conversion** - Smart brightness-based character selection with RGB color matching
- ✍️ **Text-to-ANSI Conversion** - Render text at any size and convert to ANSI art
- 🎯 **Interactive Manipulation** - Drag to move, corner handles to resize, rotate handle for rotation
- 📤 **Multiple Export Formats** - Copy to clipboard, download as .ans, or export as PNG
- 🎯 **Offline-First** - Runs entirely in your browser, no server required
- 🔒 **Privacy-Focused** - No data uploads, all processing happens locally
- 📱 **Responsive Design** - Split-panel UI optimized for desktop use

---

## Quick Start

### For End Users

1. Visit [https://nqrlabs.com/Ansitti/](https://nqrlabs.com/Ansitti/)
2. Choose **Block** or **ASCII** character mode
3. Click **+ Image** to upload an image or **+ Text** to add text
4. Adjust width, height, and colors before adding layers
5. Drag layers to move them, use handles to resize/rotate
6. Export as .ans, PNG, or copy to clipboard

### For Developers

```bash
# Clone the repository
git clone https://github.com/nqrlabs/nqrlabs.github.io.git
cd nqrlabs.github.io/Ansitti

# Serve locally (Python 3)
python -m http.server 8000

# Open in browser
open http://localhost:8000
```

---

## How It Works

### Image-to-ANSI Conversion Algorithm

1. **Scaling**: Source image is scaled to exact target character dimensions
2. **Brightness Calculation**: Each pixel's brightness is calculated using standard luminance formula: `0.299R + 0.587G + 0.114B`
3. **Character Selection**: Brightness value (0-1) maps to character set index
4. **Color Matching**: RGB values find closest ANSI color via Euclidean distance in RGB color space

### Character Sets

- **Block Characters**: `' ', '░', '▒', '▓', '█'` — 5 levels of shading for smooth gradients
- **ASCII Characters**: `' ', '.', ':', '-', '=', '+', '*', '#', '%', '@'` — 10 levels for classic ASCII art

### ANSI Color Standard

Standard 16-color ANSI palette:
- **Colors 0-7**: Black, Red, Green, Yellow, Blue, Magenta, Cyan, White
- **Colors 8-15**: Bright variants (Bright Black/Gray, Bright Red, Bright Green, Bright Yellow, Bright Blue, Bright Magenta, Bright Cyan, Bright White)

### Technical Details

- **Technology Stack:**
  - Pure HTML/CSS/JavaScript (no frameworks)
  - Canvas 2D API for image sampling and rendering
  - File API for image upload and download
  - Clipboard API for copy functionality

- **Processing Pipeline:**
  1. User uploads image or enters text
  2. Image scaled to character grid dimensions
  3. Each pixel analyzed for brightness and color
  4. Characters selected from active character set based on brightness
  5. Closest ANSI color assigned to each character
  6. ANSI data stored in layer with position, dimensions, rotation
  7. Preview rendered by compositing all layers in order

---

## Browser Compatibility

- ✅ **Chrome/Edge** 90+ (recommended)
- ✅ **Firefox** 88+
- ✅ **Safari** 14+
- ⚠️ **Mobile browsers** - Limited functionality due to touch interactions and screen size

**Required Web APIs:**
- Canvas 2D API (image sampling and export)
- File API (image upload)
- Blob API (file downloads)
- Clipboard API (copy to clipboard)

---

## Privacy

Ansitti runs entirely in your browser. No data is uploaded to any server:
- ✅ All data stays on your device
- ✅ No tracking or analytics
- ✅ Works offline after initial load
- ✅ No cookies or local storage
- ✅ Your images and text never leave your computer

---

## Use Cases

### For ARG Creators
- Create retro terminal-style messages for ARG websites
- Generate ANSI art clues that can be hidden in source code
- Design ASCII art puzzles with hidden layers
- Export PNG versions for social media teasers

### For Puzzle Solvers
- Convert images to ANSI for terminal-based puzzle solutions
- Create response art in ANSI format for ARG communities
- Experiment with character-based image representations

### For General Users
- Create retro ASCII/ANSI art for personal projects
- Generate terminal-style graphics for coding projects
- Design text-based logos and banners
- Experiment with creative character-based art

---

## Tips & Best Practices

- **Tip 1: Start with High Contrast** - Images with strong contrast convert better to ANSI art
- **Tip 2: Adjust Dimensions First** - Set width and height before adding layers to get the desired resolution
- **Tip 3: Block vs ASCII Mode** - Block mode works better for smooth gradients, ASCII mode for detailed textures
- **Tip 4: Layer Order Matters** - Use ↑ and ↓ buttons to reorder layers and change compositing
- **Tip 5: Experiment with Colors** - Try different foreground/background color combinations for unique effects
- **Tip 6: Zoom for Detail** - Use Zoom + to get precise placement when working with multiple layers

---

## Development

### File Structure

```
Ansitti/
├── index.html              # Main HTML file (includes all CSS/JS inline)
├── assets/
│   ├── css/
│   │   └── styles.css      # NQR Labs design system styles
│   ├── js/
│   │   └── app.js          # (Placeholder - logic is in index.html)
│   └── images/
│       ├── logo.png        # Ansitti logo
│       ├── favicon-16x16.png
│       ├── favicon-32x32.png
│       └── apple-touch-icon.png
├── LICENSE                 # MIT License
└── README.md               # This file
```

### Adding New Features

1. Update the inline `<script>` section in `index.html` with new functionality
2. Add UI controls in the control panel or preview toolbar
3. Add custom styles in the `<style>` section
4. Test thoroughly in multiple browsers
5. Update this README with documentation

### Third-Party Dependencies

**None** - Ansitti is built with pure vanilla JavaScript and uses only standard Web APIs.

---

## Known Issues

- Rotation feature may cause slight rendering artifacts on some browsers
- Very large layer counts (50+) may impact performance on older devices
- Color matching is optimized for sRGB color space

---

## Roadmap

- [ ] Undo/redo functionality
- [ ] Load/save project files
- [ ] Custom character sets
- [ ] Dithering options for better image conversion
- [ ] True ANSI escape code export with colors
- [ ] Animation support (frame-based ANSI art)

---

## Related Tools

Check out other NQR Labs tools:
- **[GlyphGrid](https://nqrlabs.com/GlyphGrid/)** - Crack cryptograms with intelligent mapping
- **[Inknigma](https://nqrlabs.com/Inknigma/)** - Hide multiple clues in images with steganography
- **[SpectroGhost](https://nqrlabs.com/SpectroGhost/)** - Hunt secret messages inside sound with spectrograms
- [View all tools](https://nqrlabs.com/)

---

## Contributing

This project is open source! Contributions, issues, and feature requests are welcome.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## License

MIT License - see [LICENSE](LICENSE) file for details.

Copyright (c) 2025 NQR

---

## Credits

- **Created by:** NQR Labs
- **Website:** [https://nqrlabs.com](https://nqrlabs.com)
- **YouTube:** [https://youtube.com/@CLU-NQR](https://youtube.com/@CLU-NQR)
- **Discord:** [Join our community](https://discord.gg/HT9YE8rvuN)
- **GitHub:** [https://github.com/NQRLabs](https://github.com/NQRLabs)

---

Made with 💙 by [NQR Labs](https://nqrlabs.com)
