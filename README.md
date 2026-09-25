# ⚡ Developer Dashboard UI

> **Clean, zero-dependency CSS component library built specifically for developer tools, dashboards, and internal web applications.**

[![Pure CSS](https://img.shields.io/badge/Dependencies-Zero-brightgreen.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Dark & Light Mode](https://img.shields.io/badge/Theme-Dark%20%26%20Light-orange.svg)](#)
[![Components: 30](https://img.shields.io/badge/Components-30%20Widgets-purple.svg)](#-component-gallery)

---

## 🌟 Why Use This Library?

Most UI libraries (like Bootstrap, Tailwind, or Material UI) are either too generic or force you to install heavy Node.js build pipelines with hundreds of megabytes of `node_modules`.

**Developer Dashboard UI is different:**
- **Zero Dependencies**: Pure HTML and CSS. No JavaScript frameworks required.
- **Made for Developers**: Includes widgets that developer tools actually need (terminal log viewers, step execution cards, folder trees, and build buttons).
- **Framework Agnostic**: Works everywhere — Python (Flask, Django, FastAPI), Go templates, Rust, Java, PHP, Node.js, HTMX, or plain HTML.
- **Dark & Light Mode**: Built-in dark theme with simple 1-attribute switching.
- **Safe Scoped Classes**: All styles use the `.ui-*` prefix, so they will never break your existing website styles.

---

## 🚀 5-Second Quick Start

Create an `index.html` file and paste this code to see it working immediately:

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Dashboard</title>
  <!-- 1. Link the stylesheet -->
  <link rel="stylesheet" href="dist/ui.css">
</head>
<body style="padding: 24px; font-family: var(--ui-font-family); background: var(--ui-bg-canvas); color: var(--ui-text-primary);">

  <!-- 2. Use UI components -->
  <div class="ui-card" data-variant="accent" style="max-width: 600px; margin: 0 auto;">
    <div class="ui-card-header">
      <h2 class="ui-card-title">⚡ System Status</h2>
      <span class="ui-badge" data-variant="success">Online</span>
    </div>
    <div class="ui-card-body">
      <p>All microservices are operational.</p>
      
      <!-- Terminal Log Viewer -->
      <div class="ui-terminal" style="margin-top: 16px;">
        <div class="ui-terminal-header">
          <div class="ui-terminal-actions">
            <span class="ui-terminal-dot" data-action="close"></span>
            <span class="ui-terminal-dot" data-action="minimize"></span>
            <span class="ui-terminal-dot" data-action="maximize"></span>
          </div>
          <div class="ui-terminal-title">build.log</div>
        </div>
        <div class="ui-terminal-body">
          <div class="ui-terminal-line" data-log="command">docker compose up -d</div>
          <div class="ui-terminal-line" data-log="success">Container db started [OK]</div>
          <div class="ui-terminal-line" data-log="info">Server listening on port 8080</div>
        </div>
      </div>
    </div>
    <div class="ui-card-footer">
      <button class="ui-button" data-variant="primary">Restart Service</button>
      <button class="ui-button" data-variant="ghost">View Logs</button>
    </div>
  </div>

</body>
</html>
```

---

## 🖥️ Live Showcase & Documentation Server

You can preview all 30 components with live copy-paste HTML snippets using the included lightweight Python server:

```bash
# Start the local showcase server
python3 server.py
```

Then open your browser to:
👉 **[http://localhost:8088/showcase/](http://localhost:8088/showcase/)**

*(Or simply open `showcase/index.html` directly in your browser!)*

---

## 📦 How to Add to Your Project

### Method 1: Direct File Copy (Recommended)
Copy `dist/ui.css` into your project's static assets folder and link it:
```html
<link rel="stylesheet" href="assets/ui.css">
```

### Method 2: NPM (For JavaScript / Node projects)
```bash
npm install developer-dashboard-ui
```
Then import it into your CSS or JS:
```css
@import "developer-dashboard-ui/dist/ui.css";
```

---

## 🎨 Themes: Dark & Light Mode

Switching between Dark Mode and Light Mode is as simple as changing the `data-theme` attribute on your `<html>` tag:

```html
<!-- Dark Theme (Default) -->
<html lang="en" data-theme="dark">

<!-- Light Theme -->
<html lang="en" data-theme="light">
```

### Changing Colors (Design Tokens)
All colors and spacing are controlled by CSS Custom Properties (variables) defined in [`components/base.css`](components/base.css). You can easily override them in your own CSS:

```css
:root {
  /* Change brand primary color to custom blue */
  --ui-primary-color: #2563eb;
  --ui-primary-hover: #1d4ed8;
  
  /* Change corner roundness */
  --ui-radius-md: 8px;
}
```

---

## 📚 Component Gallery (30 Components)

Each component has its own folder with an HTML snippet, a standalone CSS file, and a dedicated README:

| Component | Class Name | What It Is Used For | Documentation |
|---|---|---|---|
| **Terminal** | `.ui-terminal` | Console log viewer with command prompts and error highlights | [Read Docs](components/widgets/terminal/README.md) |
| **Step Card** | `.ui-step-card` | Pipeline steps with status indicators (passed, failed, pending) | [Read Docs](components/widgets/step-card/README.md) |
| **Folder Tree** | `.ui-tree` | File system tree explorer with collapsible folders and files | [Read Docs](components/widgets/tree/README.md) |
| **Command Button** | `.ui-command-button` | Build & deploy selector buttons with lock states | [Read Docs](components/widgets/command-button/README.md) |
| **App Card** | `.ui-app-card` | Microservice / app selector tile with version & health status | [Read Docs](components/widgets/app-card/README.md) |
| **Button** | `.ui-button` | Primary, secondary, outline, ghost, danger, and disabled buttons | [Read Docs](components/widgets/button/README.md) |
| **Badge** | `.ui-badge` | Status pills (success, warning, danger, neutral, primary) | [Read Docs](components/widgets/badge/README.md) |
| **Card** | `.ui-card` | Content containers with headers, footers, and accent borders | [Read Docs](components/widgets/card/README.md) |
| **Modal** | `.ui-modal` | Dialog popups and confirmation windows with backdrop | [Read Docs](components/widgets/modal/README.md) |
| **Table** | `.ui-table` | Data tables with hover states, zebra stripes, and borders | [Read Docs](components/widgets/table/README.md) |
| **Input & Form** | `.ui-input`, `.ui-select` | Text boxes, dropdowns, labels, and validation states | [Read Docs](components/widgets/input/README.md) |
| **Controls** | `.ui-checkbox`, `.ui-toggle` | Checkboxes, radio buttons, and iOS-style toggle switches | [Read Docs](components/widgets/controls/README.md) |
| **Alert** | `.ui-alert` | Banners for notifications, info, warnings, and errors | [Read Docs](components/widgets/alert/README.md) |
| **Toast** | `.ui-toast` | Floating popup alerts for transient messages | [Read Docs](components/widgets/toast/README.md) |
| **Progress** | `.ui-progress` | Loading bars and completion indicators with status colors | [Read Docs](components/widgets/progress/README.md) |
| **Loader** | `.ui-loader` | Spinners in multiple sizes and colors | [Read Docs](components/widgets/loader/README.md) |
| **Skeleton** | `.ui-skeleton` | Shimmering placeholder animations while data loads | [Read Docs](components/widgets/skeleton/README.md) |
| **Segmented Nav** | `.ui-segmented` | Tabbed pill switchers (e.g., Dev / QA / Prod) | [Read Docs](components/widgets/segmented/README.md) |
| **Navigation** | `.ui-tabs`, `.ui-breadcrumbs` | Horizontal tabs and hierarchy breadcrumbs | [Read Docs](components/widgets/navigation/README.md) |
| **Sidebar Nav** | `.ui-sidebar` | Full vertical navigation bar with active links and icons | [Read Docs](components/widgets/sidebar/README.md) |
| **Page Header** | `.ui-page-header` | Standard page titles with subtitles and action buttons | [Read Docs](components/widgets/page-header/README.md) |
| **Section Header**| `.ui-section-header` | Section dividers with titles and meta descriptions | [Read Docs](components/widgets/section-header/README.md) |
| **Layout Shell** | `.ui-page`, `.ui-grid` | Responsive grid containers and split layout panes | [Read Docs](components/widgets/layout/README.md) |
| **Tile Card** | `.ui-tile-card` | Compact dashboard grid cards for metrics and apps | [Read Docs](components/widgets/tile-card/README.md) |
| **Avatar** | `.ui-avatar` | User profile images, initials circles, and avatar groups | [Read Docs](components/widgets/avatar/README.md) |
| **Tooltip** | `.ui-tooltip-trigger` | Pure CSS hover tooltips with zero JavaScript | [Read Docs](components/widgets/tooltip/README.md) |
| **Dropzone** | `.ui-dropzone` | Drag-and-drop file upload placeholder | [Read Docs](components/widgets/dropzone/README.md) |
| **Lightbox** | `.ui-lightbox` | Full-screen image preview overlay | [Read Docs](components/widgets/lightbox/README.md) |
| **Modal Tabs** | `.ui-modal-tabs` | Sub-navigation tabs embedded inside modal dialogs | [Read Docs](components/widgets/modal-tabs/README.md) |
| **Typography** | `.ui-title`, `.ui-code` | Consistent headings, code blocks, links, and text styles | [Read Docs](components/widgets/typography/README.md) |

---

## 🛠️ Making Changes & Building

If you modify any widget styles inside `components/`, re-build the distribution file by running:

```bash
python3 bundle.py
```

This updates both `dist/ui.css` and `dist/developer-dashboard-ui.css`.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE) — free to use in personal, open-source, or commercial projects!
