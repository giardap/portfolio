# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal portfolio website showcasing blockchain development, security research, and software engineering projects. The site is built as a single-page application with modern HTML5, CSS3, and vanilla JavaScript, featuring a dark theme design with glassmorphism effects and responsive mobile-first architecture.

## Architecture & Structure

### Core Files
- `index.html` - Main HTML file with complete portfolio content and embedded JavaScript
- `style.css` - Primary stylesheet with CSS custom properties and responsive design
- `mobile-fixes.css` / `mobile-critical-fixes.css` - Mobile-specific styling overrides
- `icons.js` - Phosphor icon system with SVG definitions
- `portfolio_data.json` - Project metadata and GitHub repository information

### Design System
**CSS Custom Properties (`:root`):**
- Color system with dark theme variables (`--color-bg-*`, `--color-text-*`, `--color-accent-*`)
- Typography scale using Bai Jamjuree and Inter fonts
- Spacing system (`--space-xs` to `--space-5xl`)
- Border radius scale (`--radius-sm` to `--radius-pill`)
- Shadow and glassmorphism effects (`--glass-*`, `--shadow-*`)
- Animation durations and easing functions

**Component Architecture:**
- Modular CSS with BEM-like naming conventions
- Responsive breakpoints: mobile-first approach with desktop overrides
- Floating dock navigation system with active state tracking
- Section-based layout (hero, about, projects, experience, research, contact)

### JavaScript Architecture
**Core Functionality:**
- Smooth scrolling navigation with intersection observer
- Mobile hamburger menu toggle
- Active section tracking for navigation states
- Icon system initialization with Phosphor icons
- Scroll-based navbar hide/show behavior
- Responsive floating dock with hover effects

**Key JavaScript Patterns:**
- Event delegation for navigation links
- Intersection Observer API for section visibility
- ResizeObserver for responsive behavior
- Module pattern for icon management

## Development Workflow

### File Serving
No build process required - static files served directly. Can be opened locally or served via:
- Live Server extension for VS Code
- Python: `python -m http.server 8000`
- Node.js: `npx serve .`

### Mobile Development
Critical mobile fixes are applied via separate CSS files with `!important` overrides:
- `mobile-fixes.css` - General mobile adjustments
- `mobile-critical-fixes.css` - Critical layout fixes with high specificity

### Asset Management
- Icons managed through `icons.js` with inline SVG definitions
- Images stored in root directory (`logo.png`, `logo2.png`, etc.)
- Resume PDF stored in `assets/` directory

## Key Features & Patterns

### Navigation System
- Dual navigation: top navbar (desktop) and floating dock (mobile-enhanced)
- Intersection Observer-based active state management
- Smooth scrolling with CSS `scroll-behavior` and JavaScript fallbacks

### Responsive Design
- Mobile-first CSS architecture
- Desktop optimizations with `@media (min-width: 769px)`
- Critical mobile layout fixes for complex sections (research, experience)
- Compact mobile layouts with truncated content

### Icon System
Custom Phosphor icon implementation with:
- SVG-based icons with `currentColor` inheritance
- Dynamic icon injection via JavaScript
- Consistent sizing and styling across components

### Performance Optimizations
- Inline critical CSS in HTML for above-the-fold content
- Intersection Observer for lazy animations
- CSS containment and GPU acceleration hints
- Minimal JavaScript with efficient event handling

## Styling Conventions

### CSS Organization
1. Reset and base styles
2. CSS custom properties (design tokens)
3. Typography and global styles
4. Component styles (navbar, hero, sections)
5. Responsive overrides
6. Mobile-specific fixes (separate files)

### Color Usage
- Primary accent: `--color-accent-purple` (purple theme)
- Secondary accent: `--color-accent-green` (success states)
- Text hierarchy: primary, secondary, muted variants
- Background layers: primary, secondary, tertiary, card variants

### Animation Patterns
- CSS transitions with custom easing functions
- Transform-based animations for performance
- Intersection Observer triggers for scroll animations
- Hover and focus state transitions

## Content Management

Portfolio content is managed through:
- HTML sections for static content
- `portfolio_data.json` for project metadata
- Inline project cards with GitHub integration
- Resume PDF in assets directory

When updating projects or experience, modify the relevant HTML sections in `index.html` and update `portfolio_data.json` for consistency.