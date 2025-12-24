# Research Medical LLM Project

## Project Overview

This is an Astro-based static site for documenting and presenting benchmarks and analysis of medical Large Language Models (LLMs) and Vision Language Models (VLMs). The project compares open-source and proprietary solutions in the medical domain, providing performance metrics, cost analysis, and methodology documentation.

The site is built with Astro (version 5.16.6) and follows the standard Astro project structure. It includes documentation pages comparing LLMs (including Grok), VLMs for document understanding, cost analysis of different deployment options, and benchmarking methodology.

### Key Technologies
- **Astro** (v5.16.6): Static site generator
- **TypeScript**: Type-safe development
- **Markdown**: Documentation content
- **CSS**: Styling

### Project Structure
```
/
├── public/           # Static assets
├── src/
│   ├── components/   # Reusable Astro components (Header, Layout, Sidebar)
│   ├── pages/        # Route-based pages and documentation
│   │   ├── docs/     # Documentation files (LLM/VLM benchmarks, cost analysis, methodology)
│   │   └── index.astro # Main landing page
│   └── styles/       # Global styles
├── astro.config.mjs  # Astro configuration
├── package.json      # Project dependencies and scripts
└── tsconfig.json     # TypeScript configuration
```

## Building and Running

### Development Commands
- `npm install` - Install dependencies
- `npm run dev` - Start local development server at `localhost:4321`
- `npm run build` - Build production site to `./dist/`
- `npm run preview` - Preview the build locally before deploying
- `npm run astro ...` - Run Astro CLI commands (e.g., `astro add`, `astro check`)

### Project Setup
1. Install dependencies: `npm install`
2. Start development server: `npm run dev`
3. Visit `http://localhost:4321` in your browser

The project uses Astro's file-based routing system where each `.astro` or `.md` file in the `src/pages/` directory becomes a route based on its file name.

## Development Conventions

### File Types
- `.astro` files: Astro components/pages with route-based routing
- `.md` files: Markdown documentation pages
- `.css` files: Styles (global and component-scoped)

### TypeScript Configuration
The project uses Astro's strict TypeScript configuration (`astro/tsconfigs/strict`) which enforces type safety and best practices.

### Component Architecture
- `Layout.astro`: Main layout component
- `Header.astro`: Site header component
- `Sidebar.astro`: Navigation sidebar component

### Documentation Structure
The documentation is organized in the `src/pages/docs/` directory with files for:
- LLM Benchmarks
- VLM Benchmarks
- Cost Analysis
- Methodology

## Content Strategy
The site is designed to present medical AI benchmarking data with a focus on:
- Comparative analysis of open-source vs proprietary models
- Performance metrics for medical applications
- Cost considerations for deployment
- Transparent methodology documentation