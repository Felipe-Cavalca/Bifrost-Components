# BifrostPHP Components

[![Repo](https://img.shields.io/badge/Bifrost-Components-blue)](./)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)
[![Latest Release](https://img.shields.io/github/v/release/Felipe-Cavalca/BifrostPHP-Components)](https://github.com/Felipe-Cavalca/BifrostPHP-Components/releases/latest)

> A lightweight and powerful solution for creating reusable HTML components with zero dependencies

## 🚀 Features

- ✨ **Zero Dependencies** - Pure vanilla JavaScript
- 🎯 **Simple Integration** - Just one script file
- 🔧 **Highly Customizable** - Configure paths and prefixes
- 🎨 **Shadow DOM Support** - Isolated styles and scripts
- 📦 **Component-Based** - Organize your code efficiently
- ⚡ **Fast Loading** - Optimized performance

## 📋 Table of Contents

- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Configuration](#configuration)
- [Advanced Features](#advanced-features)
- [Best Practices](#best-practices)
- [Releases](#releases)

## 📦 Installation

### Option 1: Download from Releases

1. Download the latest version of `customComponents.js` from [releases page](https://github.com/Felipe-Cavalca/BifrostPHP-Components/releases/latest)
2. Add the file to your project directory
3. Include it in your HTML:

```html
<script src="path/to/customComponents.js"></script>
```

### Option 2: CDN (Coming Soon)

```html
<script src="https://cdn.jsdelivr.net/gh/Felipe-Cavalca/BifrostPHP-Components@latest/customComponents.js"></script>
```

## 🎯 Quick Start

1. **Create your components folder structure:**

```
your-project/
├── components/
│   ├── navbar.html
│   ├── footer.html
│   └── header.html
├── index.html
└── customComponents.js
```

2. **Create a component** (e.g., `components/navbar.html`):

```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>

<style>
  nav {
    background-color: #333;
    padding: 1rem;
  }

  ul {
    list-style: none;
    display: flex;
    gap: 1rem;
  }

  a {
    color: white;
    text-decoration: none;
  }
</style>
```

3. **Use the component in your HTML:**

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>
  <script src="customComponents.js"></script>
</head>
<body>
  <c-navbar></c-navbar>

  <main>
    <h1>Welcome to my website!</h1>
  </main>

  <c-footer></c-footer>
</body>
</html>
```

## 📖 Usage

### Basic Usage

By default, the script looks for components in the `/components` directory. Any HTML file in this folder can be used as a component.

**Component file naming convention:**
- `navbar.html` → `<c-navbar></c-navbar>`
- `header.html` → `<c-header></c-header>`
- `footer.html` → `<c-footer></c-footer>`
- `user-card.html` → `<c-user-card></c-user-card>`

### Component Structure

Components can include HTML, CSS, and JavaScript:

```html
<!-- components/card.html -->
<div class="card">
  <h2>Card Title</h2>
  <p>Card content goes here</p>
</div>

<style>
  .card {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 1rem;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }
</style>

<script>
  // Component-specific JavaScript
  console.log('Card component loaded');
</script>
```

## ⚙️ Configuration

### Custom Path and Prefix

You can customize the components path and tag prefix:

```html
<script
  path="/my-components"
  prefix="app-"
  src="customComponents.js">
</script>
```

With this configuration:
- Components are loaded from `/my-components/`
- Use tags like `<app-navbar></app-navbar>`

### Configuration Options

| Attribute | Default | Description |
|-----------|---------|-------------|
| `path` | `/components` | Directory where components are stored |
| `prefix` | `c-` | Prefix for component tags |

### Examples

**Using a different prefix:**
```html
<script prefix="v-" src="customComponents.js"></script>
<!-- Use: <v-navbar></v-navbar> -->
```

**Using a different path:**
```html
<script path="/widgets" src="customComponents.js"></script>
<!-- Loads from /widgets/ directory -->
```

**Combining both:**
```html
<script path="/ui-components" prefix="ui-" src="customComponents.js"></script>
<!-- Use: <ui-navbar></ui-navbar> from /ui-components/ -->
```

## 🔥 Advanced Features

### Shadow DOM Isolation

Components are loaded using Shadow DOM, which provides:

**Benefits:**
- ✅ Style encapsulation - Component styles don't leak out
- ✅ Script isolation - Component scripts are contained
- ✅ No naming conflicts - Use same class names in different components

**Important Notes:**
- ⚠️ External styles won't affect component internals
- ⚠️ Component styles won't affect the page
- 💡 Use CSS custom properties (variables) for theming across components

### Passing Data to Components

You can pass data using custom attributes:

```html
<c-user-card name="John Doe" role="Developer"></c-user-card>
```

Access in component:
```javascript
<script>
  const name = this.getAttribute('name');
  const role = this.getAttribute('role');
  console.log(`${name} - ${role}`);
</script>
```

## 💡 Best Practices

1. **Organize Components by Feature**
   ```
   components/
   ├── layout/
   │   ├── navbar.html
   │   └── footer.html
   ├── ui/
   │   ├── button.html
   │   └── card.html
   └── forms/
       └── input.html
   ```

2. **Keep Components Small and Focused**
   - Each component should have a single responsibility
   - Break complex components into smaller ones

3. **Use Semantic Naming**
   - `user-profile.html` instead of `profile.html`
   - `product-card.html` instead of `card.html`

4. **Document Your Components**
   - Add comments explaining component usage
   - Include examples in component files

5. **Performance Tips**
   - Minimize component size
   - Avoid heavy JavaScript in components
   - Use lazy loading for non-critical components

## 🔄 Releases

### Automated Pre-releases

When a Pull Request is approved and merged, our GitHub Actions workflow automatically:
- Creates a new pre-release version
- Runs automated tests
- Generates release notes
- Publishes to the pre-release channel

This allows testing new features in a staging environment before official release.

### Official Releases

Official stable releases are created manually after:
- ✅ Pre-release testing is complete
- ✅ All features are verified
- ✅ Documentation is updated
- ✅ Breaking changes are documented

[View all releases →](https://github.com/Felipe-Cavalca/BifrostPHP-Components/releases)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](./CONTRIBUTING.md) for details.

### Development Setup

1. Fork the repository
2. Clone your fork
3. Create a feature branch
4. Make your changes
5. Submit a pull request

---

Made with ❤️