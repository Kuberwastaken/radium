# Radium Custom Fonts Configuration

This directory contains the font configuration for Radium browser, which uses:

- **Inter** - Primary UI font for all interface elements
- **JetBrains Mono** - Monospace font for code, terminal, and developer tools

## Font Files Required

To complete the font setup, you need to add the following font files to the Chromium resources:

### Inter Font Files
Place these in `chrome/browser/resources/css/`:
- `inter.css` - Inter font CSS file
- `inter-*.woff2` - Inter font files (Regular, Medium, SemiBold, Bold)

### JetBrains Mono Font Files  
Place these in `chrome/browser/resources/css/`:
- `jetbrains-mono.css` - JetBrains Mono font CSS file
- `jetbrains-mono-*.woff2` - JetBrains Mono font files (Regular, Medium, SemiBold, Bold)

## Font CSS Structure

The font CSS files should follow this structure:

```css
@font-face {
  font-family: 'Inter';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url('chrome://resources/css/inter-regular.woff2') format('woff2');
}

@font-face {
  font-family: 'JetBrains Mono';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url('chrome://resources/css/jetbrains-mono-regular.woff2') format('woff2');
}
```

## Implementation

The font configuration is implemented through:

1. **`radium-fonts.css`** - Global font variables and base styles
2. **`custom-fonts.patch`** - Updates core CSS files to use Inter/JetBrains Mono
3. **`custom-fonts-ui.patch`** - Updates UI components to use new fonts
4. **`include-radium-fonts.patch`** - Includes the font CSS in browser pages

## Font Fallback Stack

- **Primary**: Inter → Roboto → Noto Sans → Lucida Grande → Helvetica → Arial → sans-serif
- **Monospace**: JetBrains Mono → Source Code Pro → Consolas → Monaco → Courier New → monospace

## Privacy Considerations

- All fonts are loaded locally from `chrome://resources/`
- No external font requests to Google Fonts or other CDNs
- Maintains privacy while providing modern typography
