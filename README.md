# Research Medical LLM & VLM Benchmarks

This is an Astro-based static site for documenting and presenting benchmarks and analysis of medical Large Language Models (LLMs) and Vision Language Models (VLMs). The project compares open-source and proprietary solutions in the medical domain, providing performance metrics, cost analysis, and methodology documentation.

## Features

- Comprehensive benchmarks for medical LLMs and VLMs
- Cost analysis comparing API vs self-hosted solutions
- Detailed performance metrics across various medical benchmarks
- Comparison of open-source vs proprietary models
- Responsive design for all device sizes

## Project Structure

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

## Getting Started

### Prerequisites

- Node.js (version 18 or higher)
- npm or yarn package manager

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/appleinautumn/research-medical-llm.git
   cd research-medical-llm
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

### Running the Project

- **Development**: `npm run dev` - Starts the development server at `http://localhost:4321/research-medical-llm/`
- **Build**: `npm run build` - Creates a production build in the `./dist/` directory
- **Preview**: `npm run preview` - Previews the production build locally

## Documentation Sections

1. **LLM Benchmarks**: Performance analysis of medical language models across various benchmarks including ClinBench, USMLE, MedQA, and others.
2. **VLM Benchmarks**: Evaluation of Vision Language Models for document understanding tasks in medical contexts.
3. **Cost Analysis**: Comparison between API-based and self-hosted deployment options for medical AI models.
