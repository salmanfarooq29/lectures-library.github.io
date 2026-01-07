# Zahi - Arabic Digital Garden Hugo Theme

![Zahi Hugo Theme](https://raw.githubusercontent.com/mohamedelhefni/zahi/main/images/screenshot.png)

Zahi (زاهي) is a modern, fast Hugo theme designed for Arabic content with RTL support. It's built as a digital garden / personal knowledge base with Obsidian-like features.

## Features

### Core Features
- **RTL & Arabic Optimized** - Built from the ground up for Arabic content with proper RTL layout
- **Dark/Light Mode** - Toggle between themes with smooth transitions
- **Responsive Design** - Looks great on all devices
- **Fast Performance** - Minimal JavaScript, optimized assets

### Digital Garden Features
- **Wiki-style Links** - Use `[[Page Title]]` syntax to link between notes (green = valid, red = broken)
- **Knowledge Graph** - Interactive D3.js force-directed graph showing connections between posts
- **Backlinks** - Automatically shows which pages link to the current page
- **Series Support** - Group related posts into ordered collections with progress tracking

### Content Features
- **Table of Contents** - Collapsible TOC for easy navigation
- **Reading Time** - Auto-calculated based on word count
- **Search** - Fast client-side search with Fuse.js (Ctrl+K / Cmd+K)
- **Tags** - Organize content with tags
- **Syntax Highlighting** - Beautiful code blocks
- **Disqus Comments** - Optional comment integration

## Demo

Live demo: [https://zahi.netlify.app/](https://zahi.netlify.app/)

## Installation

### Method 1: Git Submodule (Recommended)

```bash
cd your-hugo-site
git submodule add https://github.com/mohamedelhefni/zahi.git themes/zahi
```

### Method 2: Hugo Module

Add to your `hugo.toml`:

```toml
[module]
  [[module.imports]]
    path = "github.com/mohamedelhefni/zahi"
```

Then run:

```bash
hugo mod get -u
```

### Method 3: Direct Download

Download the theme and extract it to `themes/zahi` in your Hugo site.

## Configuration

Add to your `hugo.toml`:

```toml
theme = "zahi"
languageCode = "ar"
defaultContentLanguage = "ar"

[taxonomies]
tag = "tags"
series = "series"

[outputs]
home = ["HTML", "RSS", "JSON"]

[params]
description = "وصف موقعك"
author = "اسمك"

[params.social]
twitter = "username"
github = "username"
linkedin = "username"

[menu]
[[menu.main]]
name = "الرئيسية"
url = "/"
weight = 1

[[menu.main]]
name = "المقالات"
url = "/posts/"
weight = 2

[[menu.main]]
name = "الوسوم"
url = "/tags/"
weight = 3

[[menu.main]]
name = "السلاسل"
url = "/series/"
weight = 4

[[menu.main]]
name = "الشبكة"
url = "/graph/"
weight = 5
```

## Content

### Basic Post

```yaml
---
title: "عنوان المقالة"
date: 2024-01-15
tags: ["وسم1", "وسم2"]
toc: true
---

محتوى المقالة...
```

### Wiki Links

Link to other posts using wiki-style syntax:

```markdown
اقرأ المزيد في [[عنوان صفحة أخرى]]
```

### Series

Create a series by adding to frontmatter:

```yaml
---
title: "الجزء الأول: المقدمة"
series: "اسم السلسلة"
seriesOrder: 1
seriesDescription: "وصف السلسلة"
---
```

### Pinned Posts

Pin posts to the homepage:

```yaml
---
title: "مقالة مثبتة"
pinned: true
---
```

## Development

### Prerequisites

- Hugo Extended v0.112.0+
- Node.js (for Tailwind CSS)

### Setup

```bash
# Clone the repository
git clone https://github.com/mohamedelhefni/zahi.git
cd zahi

# Install dependencies
pnpm install

# Start Hugo server
cd exampleSite && hugo server

# Watch Tailwind CSS (in another terminal)
npx tailwindcss -i ./static/css/style.css -o ./static/css/output.css --watch
```

### Build CSS

```bash
npx tailwindcss -i ./static/css/style.css -o ./static/css/output.css --minify
```

## Directory Structure

```
zahi/
├── archetypes/
├── exampleSite/          # Demo site
├── images/
│   ├── screenshot.png    # Theme screenshot
│   └── tn.png           # Thumbnail
├── layouts/
│   ├── _default/
│   ├── graph/           # Knowledge graph pages
│   ├── partials/
│   ├── series/          # Series taxonomy
│   └── shortcodes/
├── static/
│   ├── css/
│   └── js/
├── hugo.toml            # Hugo version requirements
├── theme.toml           # Theme metadata
└── README.md
```

## Credits

- [IBM Plex Sans Arabic](https://fonts.google.com/specimen/IBM+Plex+Sans+Arabic) - Font
- [Tailwind CSS](https://tailwindcss.com/) - Styling
- [D3.js](https://d3js.org/) - Knowledge graph
- [Fuse.js](https://fusejs.io/) - Search

## License

[MIT License](LICENSE)

## Author

**Mohamed Elhefni**
- GitHub: [@mohamedelhefni](https://github.com/mohamedelhefni)
