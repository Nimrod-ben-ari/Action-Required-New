# JSON to Markdown Viewer

A lightweight, local tool to preview JSON content as clean, readable Markdown. Perfect for reviewing `Action_Required_Table` and other JSON files visually.

## Features

- 📄 **Simple Setup** - Single HTML file, no build process required
- 🎨 **Clean UI** - Minimal, readable interface with good typography
- 📁 **Drag & Drop** - Easy file selection via drag-and-drop or file picker
- 📊 **Stats Display** - Shows entry counts (titles, bodies, etc.)
- 🔍 **Grouped View** - Automatically groups related entries (title/body pairs)
- ✨ **Markdown Rendering** - Properly renders Markdown with syntax highlighting

## Quick Start

### Option 1: Direct File Opening (Simplest)

1. Open `json-markdown-viewer.html` in your web browser
2. Click "Click to select or drag & drop a JSON file"
3. Select your `Action_Required_Table` file
4. View the rendered Markdown content

### Option 2: Local Server (Recommended for CORS)

If you encounter CORS issues when opening the file directly, use a simple local server:

```bash
# Using Python 3
python3 -m http.server 8000

# Or using Python 2
python -m SimpleHTTPServer 8000

# Or using Node.js (if you have http-server installed)
npx http-server -p 8000
```

Then open: `http://localhost:8000/json-markdown-viewer.html`

## Usage

1. **Load a JSON file:**
   - Click the file input area, or
   - Drag and drop a JSON file onto the input area

2. **View the content:**
   - The tool automatically groups entries by ID (e.g., G004, A014)
   - Shows titles as headers
   - Renders body content as Markdown
   - Displays Relops versions separately when available

3. **Switch files:**
   - Simply drag and drop or select another JSON file to re-render

## File Structure

The viewer expects JSON files with keys like:
- `title.G004` - Title entries
- `body.G004` - Body entries (Markdown content)
- `title.G004.Relops` - Relops title versions
- `body.G004.Relops` - Relops body versions

## Features in Detail

### Stats Panel
Shows at a glance:
- Total entries in the file
- Number of title entries
- Number of body entries
- Other entries count

### Grouped Display
Entries are automatically grouped by their base ID:
- `title.G004` + `body.G004` → Displayed together under "ID: G004"
- Relops versions shown separately below the main content

### Markdown Rendering
- Proper heading hierarchy
- Formatted lists (numbered and bulleted)
- **Bold** and *italic* text
- Links rendered as clickable
- Code blocks with syntax highlighting
- Proper line breaks and spacing

## Browser Compatibility

Works in all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

## No Dependencies

- Uses CDN for `marked.js` (Markdown parser) - loads automatically
- No npm, no build step, no frameworks
- Pure HTML, CSS, and JavaScript

## Troubleshooting

**File won't load:**
- Make sure you're selecting a valid JSON file
- Check browser console for errors (F12)
- Try using a local server if opening file directly

**Markdown not rendering:**
- Ensure your JSON contains valid Markdown in the body fields
- Check that newlines are actual `\n` characters, not escaped `\\n`

**Styling looks off:**
- Clear browser cache and reload
- Check that the CSS is loading properly

## Customization

The viewer is a single HTML file. You can easily customize:
- Colors: Edit the CSS variables in the `<style>` section
- Layout: Modify the HTML structure
- Grouping logic: Adjust the `renderMarkdown()` function

## License

Free to use and modify for your needs.

