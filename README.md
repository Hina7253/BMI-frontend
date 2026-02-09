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


**Using Node.js:**
```bash
# Install http-server globally
npm install -g http-server

# Run server
http-server -p 8000

# Navigate to: http://localhost:8000
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

#### Method 3: Netlify CLI
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Login
netlify login

# Deploy
netlify deploy --prod
```

### Deploy to Vercel

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
cd frontend
vercel --prod
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

## 🎨 Styling

### Color Palette

```css
/* Primary Colors */
--primary-purple: #667eea;
--primary-pink: #764ba2;
--accent-pink: #f093fb;

/* Background Colors */
--bg-dark: #0f0f23;
--bg-card: rgba(17, 24, 39, 0.95);
--bg-section: rgba(31, 41, 55, 0.5);

/* Text Colors */
--text-primary: #e2e8f0;
--text-secondary: #94a3b8;
--text-muted: #64748b;

/* Status Colors */
--critical: #ef4444;
--warning: #f59e0b;
--info: #3b82f6;
--success: #10b981;
```

### Typography

```css
/* Font Stack */
font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;

/* Code Font */
font-family: 'Fira Code', 'Courier New', monospace;

/* Font Sizes */
--font-xs: 0.85em;
--font-sm: 0.9em;
--font-base: 1em;
--font-lg: 1.2em;
--font-xl: 1.5em;
--font-2xl: 2em;
--font-3xl: 3em;
```

### Animations

```css
/* Fade In */
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Slide In */
@keyframes slideIn {
    from { opacity: 0; transform: translateX(-20px); }
    to { opacity: 1; transform: translateX(0); }
}

/* Spin (Loading) */
@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

/* Gradient Shift (Background) */
@keyframes gradientShift {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.8; transform: scale(1.1); }
}
```

---

## 🔌 API Integration

### API Endpoints Used

#### 1. Health Check
```javascript
GET ${BACKEND_URL}/health

// Response:
"Code Review Service is running!"
```

#### 2. Analyze Code
```javascript
POST ${BACKEND_URL}/analyze
Content-Type: application/json

Body: {
    "code": "public class Test { ... }"
}

// Response: AnalysisResponse object
```

#### 3. Get Metrics
```javascript
POST ${BACKEND_URL}/metrics
Content-Type: application/json

Body: {
    "code": "public class Test { ... }"
}

// Response: CodeMetrics object
```

### Error Handling

```javascript
try {
    const response = await fetch(url, options);
    
    if (!response.ok) {
        throw new Error(`HTTP ${response.status}`);
    }
    
    const data = await response.json();
    // Process data
    
} catch (error) {
    // Show user-friendly error message
    displayError(error.message);
}
```

---

## 🌐 Browser Support

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | 90+ | ✅ Full |
| Firefox | 88+ | ✅ Full |
| Safari | 14+ | ✅ Full |
| Edge | 90+ | ✅ Full |
| Opera | 76+ | ✅ Full |
| IE 11 | - | ❌ Not supported |

### Required Browser Features
- ES6+ JavaScript
- Fetch API
- CSS Grid & Flexbox
- CSS Custom Properties
- Async/Await
- Template Literals

---

## ⚡ Performance

### Metrics

| Metric | Value | Target |
|--------|-------|--------|
| **First Contentful Paint** | 0.8s | < 1.0s |
| **Time to Interactive** | 1.2s | < 1.5s |
| **Total Blocking Time** | 50ms | < 100ms |
| **Cumulative Layout Shift** | 0.01 | < 0.1 |
| **Largest Contentful Paint** | 1.5s | < 2.5s |

### Optimization Techniques

```javascript
// 1. Debounced API calls
function debounce(func, wait) {
    let timeout;
    return function(...args) {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, args), wait);
    };
}

// 2. Lazy loading
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            loadComponent(entry.target);
        }
    });
});

// 3. Efficient DOM updates
// Use DocumentFragment for batch updates
const fragment = document.createDocumentFragment();
items.forEach(item => {
    const div = document.createElement('div');
    div.textContent = item;
    fragment.appendChild(div);
});
container.appendChild(fragment);
```

---

## 🐛 Troubleshooting

### Common Issues

#### Issue 1: Styles not loading
**Symptom:** Page looks broken, no colors

**Solution:**
```bash
# Check file path in index.html
<link rel="stylesheet" href="style.css">

# Verify file exists in same directory
ls -la style.css

# Check browser console for errors (F12)
```

---

#### Issue 2: JavaScript not working
**Symptom:** Buttons don't respond

**Solution:**
```bash
# Check script.js is linked
<script src="script.js"></script>

# Must be before </body> tag
# Check browser console for errors
```

---

#### Issue 3: Backend not connecting
**Symptom:** "Backend offline" message

**Solution:**
```javascript
// 1. Check BACKEND_URL in script.js
console.log(BACKEND_URL);

// 2. Test backend directly in browser
// Visit: https://your-backend.com/api/health

// 3. Check CORS configuration in backend
// Must have: @CrossOrigin(origins = "*")
```

---

#### Issue 4: PDF not downloading
**Symptom:** Button visible but nothing happens

**Solution:**
```javascript
// 1. Check jsPDF loaded
console.log(window.jspdf);

// 2. Check browser console for errors
// 3. Verify data exists
console.log(currentAnalysisData);
console.log(currentMetricsData);
```

---

#### Issue 5: Mobile layout broken
**Symptom:** Overflow, small text on mobile

**Solution:**
```css
/* Check viewport meta tag in index.html */
<meta name="viewport" content="width=device-width, initial-scale=1.0">

/* Verify responsive styles in style.css */
@media (max-width: 1200px) {
    .content {
        grid-template-columns: 1fr;
    }
}
```

---

## 📱 Responsive Design

### Breakpoints

```css
/* Desktop (default) */
@media (min-width: 1201px) {
    .content { grid-template-columns: 1fr 1fr; }
}

/* Tablet */
@media (max-width: 1200px) {
    .content { grid-template-columns: 1fr; }
    .stats { grid-template-columns: repeat(2, 1fr); }
}

/* Mobile */
@media (max-width: 768px) {
    .header h1 { font-size: 2em; }
    .button-group { grid-template-columns: 1fr; }
}
```

---

## 🔐 Security

### Best Practices Implemented

```javascript
// 1. Input sanitization
function sanitizeInput(input) {
    return input.replace(/[<>]/g, '');
}

// 2. No eval() usage
// ❌ eval(userInput)
// ✅ JSON.parse(sanitizedInput)

// 3. HTTPS only in production
const BACKEND_URL = location.protocol === 'https:' 
    ? 'https://backend.com/api'
    : 'http://localhost:8080/api';

// 4. No sensitive data in localStorage
// Only store non-sensitive analysis history
```

---

## 📊 Analytics (Optional)

### Add Google Analytics

```html
<!-- Add before </head> in index.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Track Events

```javascript
// Track analysis button clicks
function analyzeCode() {
    gtag('event', 'analyze_code', {
        'event_category': 'engagement',
        'event_label': 'code_analysis'
    });
    // ... rest of function
}
```

---

## 🔧 Development Tools

### Recommended VS Code Extensions

```
- Live Server (ritwickdey.liveserver)
- Prettier (esbenp.prettier-vscode)
- ESLint (dbaeumer.vscode-eslint)
- CSS Peek (pranaygp.vscode-css-peek)
- Auto Rename Tag (formulahendry.auto-rename-tag)
```

### Chrome DevTools Tips

```javascript
// Debug backend connection
console.log('Backend URL:', BACKEND_URL);
console.log('Backend status:', backendOnline);

// Debug analysis data
console.table(currentAnalysisData);
console.table(currentMetricsData);

// Monitor fetch requests
// Open DevTools → Network tab → Filter: Fetch/XHR
```

---

## 🎯 Future Enhancements

- [ ] Dark/Light theme toggle
- [ ] Code editor with syntax highlighting (Monaco/CodeMirror)
- [ ] Drag & drop file upload
- [ ] Analysis history (localStorage)
- [ ] Export to JSON/CSV
- [ ] Keyboard shortcuts
- [ ] Offline mode (Service Worker)
- [ ] Progressive Web App (PWA)
- [ ] Internationalization (i18n)
- [ ] Accessibility improvements (WCAG 2.1)

---

## 📝 Code Style Guide

### Naming Conventions

```javascript
// Variables: camelCase
let userName = 'John';
const apiEndpoint = '/analyze';

// Constants: UPPER_SNAKE_CASE
const BACKEND_URL = 'https://api.com';
const MAX_FILE_SIZE = 5000000;

// Functions: camelCase, verb-first
function analyzeCode() {}
function displayResults() {}
function clearAll() {}

// CSS Classes: kebab-case
.button-group {}
.issue-item {}
.metric-card {}
```

### Code Organization

```javascript
// 1. Configuration (top)
const BACKEND_URL = '...';
const FEATURES = {...};

// 2. Global state
let backendOnline = false;
let currentData = null;

// 3. Initialization
checkBackendStatus();

// 4. Core functions
async function analyzeCode() {}
function displayResults() {}

// 5. Helper functions
function formatDate() {}
function sanitize() {}

// 6. Event handlers (if any)
document.addEventListener('DOMContentLoaded', init);
```

---

## 📄 License

This frontend code is part of the Java Code Analyzer project and is licensed under the MIT License.

---

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Portfolio: [yourwebsite.com](https://yourwebsite.com)

---

## 🙏 Credits

- **jsPDF** - PDF generation library
- **Google Fonts** - Inter & Fira Code fonts
- **Netlify** - Deployment platform

---

## 📞 Support

Need help? Found a bug?

- **Issues:** [GitHub Issues](https://github.com/yourusername/repo/issues)
- **Documentation:** [Full README](../README.md)
- **Email:** your.email@example.com

---

<p align="center">
  <sub>Built with ❤️ using vanilla JavaScript</sub>
</p>

<p align="center">
  <a href="#-java-code-analyzer---frontend">⬆️ Back to Top</a>
</p>
