# CRM Schema Visualizer 📊

A beautiful, interactive desktop application that transforms JSON data from CRM systems into visual database schemas. Perfect for developers, data analysts, and anyone working with CRM data structures.

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

## ✨ Features

- **🎨 Beautiful Visual Interface** - Modern, gradient-based design with smooth animations
- **📁 Drag & Drop Upload** - Simply drag JSON files or click to browse
- **🔧 Interactive Schema Editor** - Drag tables around to organize your schema layout
- **🔍 Zoom Controls** - Zoom in/out and reset view for better visibility
- **📊 Smart Data Processing** - Automatically infers data types and handles various JSON formats
- **💾 Export Functionality** - Save processed schemas as JSON files
- **📱 Responsive Design** - Works on desktop, tablet, and mobile devices
- **⚡ Zero Dependencies** - Pure HTML, CSS, and JavaScript - no external libraries needed

## 🚀 Quick Start

### Option 1: Direct Browser Usage
1. Download the `crm-schema-visualizer.html` file
2. Double-click to open in your web browser
3. Click "Load Sample Data" to see it in action
4. Upload your own JSON files to get started!

### Option 2: Run Locally
```bash
# Clone or download the repository
git clone https://github.com/yourusername/crm-schema-visualizer.git

# Navigate to the directory
cd crm-schema-visualizer

# Open in browser (or use a local server)
open crm-schema-visualizer.html
```

### Option 3: Local Development Server
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Then open http://localhost:8000 in your browser
```

## 📋 Supported JSON Formats

The visualizer intelligently handles multiple JSON structures:

### Standard Format (Recommended)
```json
{
  "tables": [
    {
      "name": "customers",
      "fields": [
        {"name": "id", "type": "integer", "primary": true},
        {"name": "first_name", "type": "string"},
        {"name": "last_name", "type": "string"},
        {"name": "email", "type": "string"},
        {"name": "phone", "type": "string"},
        {"name": "created_at", "type": "datetime"}
      ]
    },
    {
      "name": "orders",
      "fields": [
        {"name": "id", "type": "integer"},
        {"name": "customer_id", "type": "integer"},
        {"name": "order_date", "type": "date"},
        {"name": "total_amount", "type": "decimal"},
        {"name": "status", "type": "string"}
      ]
    }
  ]
}
```

### Array Format
```json
[
  {
    "name": "products",
    "fields": [
      {"name": "id", "type": "integer"},
      {"name": "name", "type": "string"},
      {"name": "price", "type": "decimal"}
    ]
  }
]
```

### Object-Based Format (Auto-Inferred)
```json
{
  "users": [
    {"id": 1, "name": "John Doe", "email": "john@example.com"},
    {"id": 2, "name": "Jane Smith", "email": "jane@example.com"}
  ],
  "products": [
    {"id": 1, "title": "Product A", "price": 99.99},
    {"id": 2, "title": "Product B", "price": 149.99}
  ]
}
```

## 🎯 Usage Guide

### 1. Loading Data
- **Sample Data**: Click "Load Sample Data" to see a CRM schema example
- **File Upload**: Use the drag & drop area or click to browse for JSON files
- **Drag & Drop**: Simply drag your JSON file onto the upload area

### 2. Interacting with Schemas
- **Move Tables**: Click and drag table headers to reposition them
- **Zoom**: Use the zoom controls (+, -, 🔍) for better viewing
- **Field Details**: Hover over fields to see enhanced styling

### 3. Exporting
- **Export Schema**: Click "Export Schema" to download the processed JSON
- **Clear Workspace**: Use "Clear" to reset and start over

## 🛠️ Customization

### Styling
The app uses CSS custom properties for easy theming:

```css
:root {
  --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --card-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  --border-radius: 12px;
}
```

### Adding New Data Types
Extend the `inferType()` function:

```javascript
function inferType(value) {
  // Add custom type detection
  if (typeof value === 'string' && value.match(/^https?:\/\//)) {
    return 'url';
  }
  // ... existing logic
}
```

## 🖥️ Creating a Desktop App

### Using Electron
```bash
npm install -g electron
electron crm-schema-visualizer.html
```

### Using Tauri (Rust-based)
```bash
cargo install tauri-cli
# Follow Tauri setup guide with the HTML file
```

### Progressive Web App (PWA)
Add a `manifest.json` file to make it installable:

```json
{
  "name": "CRM Schema Visualizer",
  "short_name": "CRMVisualizer",
  "start_url": "./crm-schema-visualizer.html",
  "display": "standalone",
  "theme_color": "#667eea",
  "background_color": "#ffffff"
}
```

## 🔧 Data Type Detection

The app automatically detects these data types:

| Value Example | Detected Type |
|---------------|---------------|
| `123` | `integer` |
| `123.45` | `float` |
| `true` | `boolean` |
| `"2024-01-15"` | `date` |
| `"user@example.com"` | `email` |
| `"Hello World"` | `string` |
| `null` | `text` |

## 🎨 Design Features

- **Modern Gradient Backgrounds** - Beautiful purple-blue gradients
- **Glassmorphism Effects** - Translucent elements with backdrop blur
- **Smooth Animations** - Hover effects and floating elements
- **Card-Based Layout** - Clean, organized table representations
- **Responsive Grid** - Automatically adjusts to screen size

## 📱 Browser Support

- ✅ Chrome 70+
- ✅ Firefox 65+
- ✅ Safari 12+
- ✅ Edge 79+

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Issues & Support

- **Bug Reports**: Please use the GitHub Issues tab
- **Feature Requests**: Submit via GitHub Issues with the 'enhancement' label
- **Questions**: Check existing issues or create a new discussion

## 🙏 Acknowledgments

- Built with vanilla JavaScript for maximum compatibility
- Inspired by modern database design tools
- Uses CSS Grid and Flexbox for responsive layouts
- Emoji icons for better user experience

## 📊 Screenshots

*Upload your JSON files and see them transformed into beautiful visual schemas!*

---

**Made with ❤️ for the developer community**

*Star ⭐ this repository if you find it helpful!*