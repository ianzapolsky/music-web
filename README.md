# Music Graph Visualizer

A web-based tool for visualizing connections between musical artists and albums using an interactive graph. The tool automatically loads structured markdown files from a `/data/` directory and creates a dynamic, zoomable, and draggable graph visualization.

## Features

- **Interactive Graph**: Zoom, pan, and drag nodes to explore relationships
- **Color-coded Relationships**:
  - 🔵 Blue edges: Artist played on album
  - 🟣 Purple edges: Album samples another album
- **Node Types**: Different visual styles for artists (smaller circles) and albums (larger circles)
- **Automatic Data Loading**: Automatically loads markdown files from the `/data/` directory
- **Force-directed Layout**: Uses D3.js force simulation for natural node positioning

## Usage

1. Place your markdown files in the `/data/` directory
2. Open `index.html` in a web browser
3. The graph will automatically load and display the relationships
4. Use mouse to zoom, pan, and drag nodes
5. The graph uses a force-directed layout that settles into a natural arrangement

## Markdown File Format

The tool uses a MusicDB format with specific sections for relationships. Files are automatically detected as albums or artists based on their content.

### Album Files
```markdown
# Album: [Album Title]

**Title:** [Album Title]
**Year:** [Year]
**Genre:** [Genre]
**Artists:** [Artist 1, Artist 2, ...]
**Description:** [Album description]

## Artists

- [[Artist Name 1]]
- [[Artist Name 2]]

## Samples

- [[Sampled Album Name 1]]
- [[Sampled Album Name 2]]
```

### Artist Files
```markdown
# Artist: [Artist Name]

**Name:** [Artist Name]
**Instruments:** [Instrument 1, Instrument 2, ...]
**Genre:** [Genre]
**Bio:** [Brief biography]
```

## Relationship Types

The parser recognizes these relationship patterns:

- **Artist-Album**: Links are created when an album's `Artists` section contains `[[Artist Name]]`
- **Sampling**: Links are created when an album's `Samples` section contains `[[Album Name]]`

## Example Files

The `data/` directory contains sample markdown files demonstrating the format:
- `Davis, Miles.md` - Artist file
- `Coltrane, John.md` - Artist file
- `Kind of Blue.md` - Album file
- `Illmatic.md` - Album file
- `Stakes Is High.md` - Album file

## Technical Details

- Built with vanilla JavaScript and D3.js
- Modular code structure with separate HTML, CSS, and JavaScript files
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
├── script.js               # JavaScript functionality
├── data/                   # Markdown files directory
│   ├── Davis, Miles.md
│   ├── Coltrane, John.md
│   ├── Kind of Blue.md
│   ├── Illmatic.md
│   ├── Stakes Is High.md
│   └── ... (other artist and album files)
└── README.md               # This file
```
