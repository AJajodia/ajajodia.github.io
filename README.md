# Anu's Wiki

A personal wiki on probability and statistics, built with [Foliate](https://yyahn.com/wiki/Software/foliate/).

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (for Foliate CLI)
- Git (for version control)

### Installation

1. Clone this repository
2. Install Foliate:
   ```bash
   npm install -g foliate
   ```

### Build

Build the static site:
```bash
foliate build
```

The output will be in the `dist/` directory.

### Development

Run a local development server:
```bash
foliate serve
```

Then visit `http://localhost:3000` to view your wiki.

### Publishing

The `dist/` directory contains the static site ready to deploy to:
- GitHub Pages
- Netlify
- Vercel
- Any static host

Update the `url` field in `foliate.yaml` with your actual domain before publishing.

## Content Structure

- `00_Index.md` — Wiki index and entry point
- `01_Probability_Basics.md` through `12_Bayesian_Computation.md` — Subject matter notes
- `images/` — Image assets
- `.obsidian/` — Obsidian configuration (excluded from build)

## Configuration

Edit `foliate.yaml` to customize:
- Site title and description
- Navigation menu
- Build settings
- Asset directories
