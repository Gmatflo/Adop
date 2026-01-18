# AGENTS.md

This file contains guidelines and commands for agentic coding agents working in this repository.

## Project Overview

This is a simple interactive Valentine's Day web application that creates an engaging "Will you be my girlfriend?" experience with animated GIFs, dynamic buttons, and responsive interactions.

## Build/Lint/Test Commands

### Development Commands
```bash
# Start a local development server (recommended)
npx serve . -p 3000

# Alternative: Use Python's built-in server
python -m http.server 8000

# Alternative: Use Node.js http-server
npx http-server . -p 8000
```

### Validation Commands
```bash
# HTML validation
npx html-validate index.html

# CSS validation (via W3C API - requires manual check)
# Visit: https://jigsaw.w3.org/css-validator/validator

# JavaScript linting
npx eslint script.js

# JavaScript formatting
npx prettier --write script.js

# Check for broken links
npx link-checker https://localhost:3000
```

### Testing Commands
```bash
# No automated tests currently configured
# Manual testing checklist:
# 1. Load page and verify initial GIF displays
# 2. Verify "No" button moves when hovered
# 3. Verify "Sí" button grows when "No" button is hovered
# 4. Click "Sí" and verify happy GIF sequence
# 5. Verify all external GIF URLs load correctly
```

## Code Style Guidelines

### HTML Structure
- Use semantic HTML5 elements appropriately
- Maintain proper document hierarchy (h1, h2, etc.)
- Include alt text for all images
- Use Spanish language attribute: `<html lang="es">`
- Keep external resource loading at end of body

### CSS Conventions
- Use kebab-case for class and ID names
- Group related styles together
- Use CSS variables for repeated values
- Maintain mobile-first responsive design
- Include vendor prefixes for animations
- Use relative units (%, vh, vw) for responsive layouts

### JavaScript Standards
- Use camelCase for variable and function names
- Declare variables with `let` or `const` (avoid `var`)
- Use modern ES6+ features when appropriate
- Add descriptive comments for complex logic
- Handle events with proper event listeners
- Use meaningful variable names in Spanish when appropriate

### File Organization
```
/
├── index.html          # Main HTML structure
├── styles.css          # All styling
├── script.js           # All JavaScript logic
├── README.md           # Project documentation
└── AGENTS.md           # This file
```

## External Dependencies

### CDN Resources
- No external CSS/JS frameworks used
- Custom fonts: 'Pacifico' (Google Fonts) for message styling
- External GIF hosting: https://encoded.pe/sanvalentin/

### Browser Compatibility
- Target modern browsers (Chrome 70+, Firefox 65+, Safari 12+)
- Uses modern JavaScript features (arrow functions, const/let)
- CSS animations and transitions supported

## Interactive Features

### Button Behaviors
- "Sí" button: Grows progressively when "No" button is hovered
- "No" button: Moves to random position on hover
- Both buttons have hover effects and transitions

### GIF Sequences
- Initial GIF displays on page load
- Sad GIF sequence plays automatically
- Happy GIF sequence triggers on "Sí" click
- All GIFs have specific timing (2.5s intervals)

### State Management
- Track button hover states
- Manage timeout IDs for cleanup
- Handle early click scenarios
- Control GIF visibility states

## Common Issues & Solutions

### GIF Loading
- Ensure external GIF URLs are accessible
- Add fallback images if needed
- Consider preloading critical GIFs

### Button Positioning
- Test "No" button movement on different screen sizes
- Ensure buttons don't move outside viewport
- Handle mobile touch events appropriately

### Performance
- Clean up timeouts when user clicks early
- Optimize GIF sizes for faster loading
- Consider lazy loading for non-critical GIFs

## Deployment Notes

### Static Hosting
- Suitable for GitHub Pages, Netlify, Vercel
- No build process required
- Ensure proper MIME types for GIF files

### HTTPS Requirements
- External GIF URLs use HTTPS
- Consider mixed content issues
- Test on secure hosting environments

## Localization

### Language Support
- Primary language: Spanish
- Text content in HTML and JavaScript
- Consider adding English version if needed

### Cultural Considerations
- Valentine's Day theme appropriate for target audience
- Animation timing suitable for engagement
- Message tone friendly and romantic