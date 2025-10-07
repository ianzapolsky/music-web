# Music Graph Visualizer

A web-based tool for visualizing connections between musical artists and albums using an interactive graph. The tool reads structured markdown files and creates a dynamic, zoomable, and draggable graph visualization.

## Features

- **Interactive Graph**: Zoom, pan, and drag nodes to explore relationships
- **Color-coded Relationships**:
  - 🔵 Blue edges: Artist played on album
  - 🟣 Purple edges: Album samples another album
  - 🟢 Green edges: Album covers another album
- **Node Types**: Different visual styles for artists (smaller circles) and albums (larger circles)
- **Hover Tooltips**: Detailed information about artists and albums
- **File Input**: Load multiple markdown files from a directory

## Usage

1. Open `index.html` in a web browser
2. Click "Load Markdown Files" and select a directory containing `.md` files
3. The graph will automatically generate and display the relationships
4. Use mouse to zoom, pan, and drag nodes
5. Hover over nodes to see detailed information

## Markdown File Format

### Artist Files
```markdown
# Artist: [Artist Name]

**Name:** [Artist Name]
**Instruments:** [Instrument 1, Instrument 2, ...]
**Genre:** [Genre]
**Bio:** [Brief biography]

## Relationships

[Artist Name] played on [Album Title]
```

### Album Files
```markdown
# Album: [Album Title]

**Title:** [Album Title]
**Year:** [Year]
**Genre:** [Genre]
**Artists:** [Artist 1, Artist 2, ...]
**Description:** [Album description]

## Relationships

[Album Title] samples [Other Album Title]
[Album Title] covers [Other Album Title]
```

## Relationship Types

The parser recognizes these relationship patterns:

- **Artist-Album**: `[Artist] played on [Album]` or `[Album] features [Artist]`
- **Sampling**: `[Album A] samples [Album B]` or `[Album A] sampled by [Album B]`
- **Covering**: `[Album A] covers [Album B]` or `[Album A] covered by [Album B]`

## Example Files

The `examples/` directory contains sample markdown files demonstrating the format:
- `miles-davis.md` - Artist file
- `john-coltrane.md` - Artist file
- `kind-of-blue.md` - Album file
- `giant-steps.md` - Album file
- `a-love-supreme.md` - Album file

## Technical Details

- Built with vanilla JavaScript and D3.js
- No build process required - just open in a browser
- Responsive design that works on desktop and mobile
- Force-directed graph layout with collision detection

## Browser Compatibility

- Modern browsers with ES6 support
- Chrome, Firefox, Safari, Edge (recent versions)
- Requires JavaScript enabled

## File Structure

```
music-web/
├── index.html              # Main HTML file
├── styles.css              # CSS styles
├── main.js                 # Main application logic
├── markdown-parser.js      # Markdown parsing functionality
├── graph-visualizer.js     # D3.js graph visualization
├── examples/               # Sample markdown files
│   ├── miles-davis.md
│   ├── john-coltrane.md
│   ├── kind-of-blue.md
│   ├── giant-steps.md
│   └── a-love-supreme.md
└── README.md               # This file
```
