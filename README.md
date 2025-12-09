# NAMS Whitepapers

A Hugo-based static site for publishing whitepapers and research documents.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Hugo Extended** (version 0.30 or higher)
  - Download from: https://gohugo.io/getting-started/installing/
  - **Important**: You need the **Extended** version (not the regular version) for SCSS/SASS support
  - Verify installation: `hugo version` (should show "extended" in the output)
  
- **Git** (for cloning and managing submodules)
  - Download from: https://git-scm.com/downloads

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/nams-design/papers.git
cd papers
```

### 2. Initialize Theme Submodules

This project uses Git submodules for themes. Initialize and update them:

```bash
git submodule update --init --recursive
```

This will download the required themes:
- `hello-friend-ng` (main theme)
- `ananke` (optional theme)

### 3. Run Hugo Development Server

Start the local development server:

```bash
hugo server
```

Or with the development environment explicitly:

```bash
hugo server --environment development
```

The site will be available at `http://localhost:1313/`

### 4. Build for Production

To build the static site:

```bash
hugo --environment production
```

The generated site will be in the `public/` directory.

## Project Structure

```
papers/
├── config/              # Hugo configuration files
│   ├── _default/        # Default config (localhost)
│   └── production/     # Production config (GitHub Pages)
├── content/            # Content files (markdown)
│   └── papers/        # Whitepaper posts
├── layouts/           # Custom layouts and partials
├── static/            # Static files (images, etc.)
└── themes/            # Theme submodules
```

## Configuration

- **Local Development**: Uses `config/_default/hugo.toml` (baseURL: `http://localhost:1313/`)
- **Production**: Uses `config/production/hugo.toml` (baseURL: `https://nams-design.github.io/papers/`)

## Features

- Dark/Light mode toggle (top right corner)
- Author information with avatars
- Responsive design
- GitHub Pages deployment via GitHub Actions

## Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the `main` branch via GitHub Actions.

See `.github/workflows/gh-pages.yml` for the deployment configuration.

## Adding Content

Create new whitepapers in `content/papers/`:

```bash
hugo new papers/my-whitepaper.md
```

Edit the front matter to include author information:

```yaml
---
title: "My Whitepaper"
date: 2025-12-09T12:00:00+05:30
draft: false
author:
  name: "Author Name"
  avatar: "/images/avatar.png"
  bio: "Author bio"
---
```

## Troubleshooting

### Theme not loading?

Make sure submodules are initialized:
```bash
git submodule update --init --recursive
```

### CSS not working?

Ensure you're using Hugo **Extended** version:
```bash
hugo version
```
Should show "extended" in the output.

### Port already in use?

Use a different port:
```bash
hugo server --port 1314
```
