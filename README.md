# 🎨 Java Code Analyzer - Frontend

> Modern, responsive web interface for Java code analysis with real-time feedback and beautiful visualizations

[![Netlify Status](https://api.netlify.com/api/v1/badges/your-badge-id/deploy-status)](https://app.netlify.com/sites/your-site/deploys)
[![License](https://img.shields.io/badge/license-MIT-green)](../LICENSE)

---

## 🌟 Overview

A sleek, modern single-page application (SPA) built with vanilla JavaScript that provides an intuitive interface for analyzing Java code. Features include real-time code analysis, metrics visualization, and professional PDF report generation.

**Live Demo:** [https://javacodereview.netlify.app](https://javacodereview.netlify.app)

---

## ✨ Features

### 🔍 **Code Analysis Interface**
- Syntax-aware textarea with monospace font
- Real-time character counting
- Responsive layout
- Copy/paste support

### 📊 **Metrics Dashboard**
- Visual progress bars
- Animated counters
- Circular quality score indicator
- Color-coded grade badges (A-F)
- Responsive metric cards

### 📄 **PDF Export**
- Client-side PDF generation using jsPDF
- Multi-page support
- Professional formatting
- Color-coded issue categories
- Automatic date stamping

### 🎨 **UI/UX**
- Dark theme with gradient accents
- Smooth animations and transitions
- Glassmorphism effects
- Responsive design (mobile-friendly)
- Accessible color contrasts
- Loading states and spinners
- Error handling with user-friendly messages

### 🚀 **Performance**
- Lazy loading
- Debounced API calls
- Optimized animations
- Minimal dependencies
- Fast initial load

---

## 🛠️ Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **HTML5** | - | Semantic markup |
| **CSS3** | - | Styling & animations |
| **JavaScript** | ES6+ | Client-side logic |
| **jsPDF** | 2.5.1 | PDF generation |
| **Fetch API** | - | HTTP requests |

**No Frameworks Used!** Pure vanilla JavaScript for optimal performance.

---

## 📁 File Structure

```
frontend/
│
├── index.html          # Main HTML structure (3KB)
├── style.css           # All styling (18KB)
├── script.js           # JavaScript logic (14KB)
│
├── screenshots/        # UI screenshots
│   ├── dashboard.png
│   ├── analysis.png
│   └── metrics.png
│
└── README.md          # This file
```

**Total Size:** ~35KB (excluding images)

---

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome 90+, Firefox 88+, Edge 90+, Safari 14+)
- Text editor (VS Code recommended)
- Basic knowledge of HTML/CSS/JS

### Local Development

#### Option 1: Direct File Opening
```bash
# 1. Download the files
git clone https://github.com/yourusername/java-code-analyzer.git
cd frontend

# 2. Open index.html in browser
# Windows:
start index.html

# Mac:
open index.html

# Linux:
xdg-open index.html
```

**Using VS Code:**
```
1. Install "Live Server" extension
2. Right-click index.html
3. Select "Open with Live Server"
```

---

## ⚙️ Configuration

### Backend URL Configuration

Open `script.js` and update the backend URL:

```javascript
// Line 7 in script.js

// For LOCAL development:
const BACKEND_URL = 'http://localhost:8080/api';

// For PRODUCTION (deployed):
const BACKEND_URL = 'https://your-backend.onrender.com/api';
```

### Feature Toggles

```javascript
// script.js - Global State Section

// Enable/disable features
const FEATURES = {
    pdfDownload: true,      // PDF export feature
    autoSave: false,        // Auto-save code (future)
    darkMode: true,         // Dark theme (default)
    animations: true        // Enable animations
};
```

---

## 🚀 Deployment

### Deploy to Netlify

#### Method 1: Drag & Drop
```
1. Go to https://app.netlify.com
2. Drag the entire frontend/ folder
3. Wait 30 seconds
4. Done! ✅
```

#### Method 2: GitHub Integration
```bash
# 1. Push to GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/repo.git
git push -u origin main

# 2. Connect in Netlify
- New site from Git
- Select repository
- Build command: (leave empty)
- Publish directory: /
- Deploy!
```

### Deploy to GitHub Pages

```bash
# 1. Create gh-pages branch
git checkout -b gh-pages

# 2. Push files
git add .
git commit -m "Deploy to GitHub Pages"
git push origin gh-pages

# 3. Enable in Settings → Pages
# Source: gh-pages branch
```

---

## 🧩 Components

### 1. Header Component
```html
<!-- Located in: index.html -->
<div class="header">
    <h1>☕ Java Code Analyzer Pro</h1>
    <p>AI-Powered Static Code Analysis</p>
</div>
```
**Styling:** Gradient background with shine animation

---

### 2. Code Editor
```html
<textarea id="codeInput" placeholder="..."></textarea>
```
**Features:**
- Monospace font (Fira Code)
- Auto-resize
- Syntax preservation
- 450px initial height

---

### 3. Button Group
```html
<div class="button-group">
    <button onclick="analyzeCode()">Analyze</button>
    <button onclick="showMetrics()">Metrics</button>
    <button onclick="clearAll()">Clear</button>
</div>
```
**Interactions:**
- Hover effects
- Click animations
- Disabled states
- Loading indicators

---

### 4. Results Container
```html
<div class="results-container" id="results">
    <!-- Dynamic content inserted here -->
</div>
```
**States:**
- Empty state (initial)
- Loading state (spinner)
- Results state (issues list)
- Error state (error message)

---

### 5. Metrics Dashboard
```javascript
// Generated dynamically in displayMetrics()
- Metric cards (4 cards in grid)
- Progress bars
- Quality score circle
- Grade badge
```

---

### 6. Floating PDF Button
```html
<button class="download-pdf-btn" id="downloadPdfBtn">
    📥 Download PDF Report
</button>
```
**Behavior:**
- Hidden by default
- Appears after analysis
- Fixed position (bottom-right)
- Slide-in animation

---







