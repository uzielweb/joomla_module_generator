# Joomla Extension Generator Professional
**The Ultimate Scaffolding Ecosystem for Modern Joomla Development (v4, v5, and v6)**

[![Launch Generator](https://img.shields.io/badge/Launch-Generator-brightgreen?style=for-the-badge&logo=joomla)](https://uzielweb.github.io/joomla_module_generator/)

## 🌟 Project Overview
The **Joomla Extension Generator** is a comprehensive ecosystem of scaffolding tools designed to eliminate repetitive tasks in Joomla extension creation. It doesn't just generate files; it implements an **enterprise-grade architecture** based on the latest Joomla core standards.

If you are a developer seeking productivity, this project offers three levels of automation to handle everything from simple modules to complex components and plugins with database logic and APIs.

---

## ⚡ Generation Tiers

This repository houses three distinct versions of the generator, each focused on a specific level of complexity:

### 1. 🟢 Basic Generator (`index.html`)
Ideal for beginners or quick modules that don't require complex configurations.
- Generates the basic structure (Dispatcher, Helper, Provider).
- Support for essential metadata and namespaces.
- Instant .ZIP package download.

### 2. 🚀 Intermediate Generator (`joomla-module-generator-intermediate.html`)
Focused on functional modules with a rich user interface.
- **+12 Ready-to-use Templates**: Hero, Carousel, FAQ, Gallery, Pricing Table, etc.
- **MVC Architecture**: Clear separation between data and display.
- **Web Asset Manager**: Automatic JS/CSS enqueuing.
- **Multilingual Support**: Automatic `.ini` file generation for multiple languages.

### 3. ⚡ Professional Generator (`joomla-module-generator-professional.html`)
The definitive tool for senior developers and agencies.
- **Fields Architect**: Visual interface to create forms with **~75 native Joomla field types**.
- **Dynamic Subforms**: Support for repeatable fields (repeatable-grid) with child fields.
- **SQL Integration**: Pre-configured database logic.
- **AJAX & REST**: Endpoints prepared for asynchronous interactions.
- **JSON Export**: Save your configurations for future editing or sharing.

---

## 🚀 Key Technical Features
- **Full Compatibility**: Guaranteed support for Joomla 4.4, Joomla 5.x, and the upcoming Joomla 6.
- **PSR Standards**: Code generated with Namespaces and Autoloading (PSR-4).
- **Service Providers**: Native implementation of the Dependency Injection pattern.
- **Modern Dispatchers**: Centralized request control according to the new Core standard.
- **Zero Dependencies**: Works entirely in the browser (Client-side) using JSZip.

---

## 🏗️ Default Joomla 5/6 Structure (Corrected)

A modern Joomla extension must follow this organization to ensure compatibility with the installer and the Namespace system:

```text
mod_hello/
├── language/
│   └── en-GB/
│       ├── mod_hello.ini        # Interface translations
│       └── mod_hello.sys.ini    # System/Installer translations
├── media/                       # Public assets (Web Assets)
│   ├── css/
│   ├── js/
│   ├── images/
│   └── joomla.asset.json        # Asset dependency definitions
├── services/
│   └── provider.php             # Registration in the Service Container (DI)
├── src/                         # Source Code (PSR-4)
│   ├── Dispatcher/
│   │   └── Dispatcher.php       # Main Controller
│   └── Helper/
│       └── HelloHelper.php      # Data/DB Logic
├── tmpl/
│   └── default.php              # Layout (View)
└── mod_hello.xml                # Extension Manifest
```

### Why JSZip?
All the generation intelligence of this project resides in **Vanilla JS** (pure JavaScript) within the HTML files themselves. **JSZip** is used exclusively to allow your browser to bundle these multiple generated files into a single downloadable `.zip` package, without requiring server-side processing.

---

## 📜 History & Evolution

This project was born from **`modulegenerator.php`**, a basic PHP script (Legacy Engine) created to automate the Joomla file structure. It is still available in this repository as a command-line tool or for direct execution via a local server.

Today, the project has evolved into a complete ecosystem of visual tools, offering a much richer and more professional development experience through web interfaces:

### 🛠️ How to Use (Choose your Version)

#### Option A: Web Interface (Recommended)
Access the **[Live Demo](https://uzielweb.github.io/joomla_module_generator/)** and choose between the **Basic, Intermediate, or Professional** versions according to your needs.

#### Option B: PHP Script (Legacy / Local Server)
1. Place the project folder on your local server (e.g., Laragon/XAMPP).
2. Access `localhost/joomla_module_generator/modulegenerator.php`.
3. Fill out the form and click **Execute** to download the `.zip`.

---

## 🏗️ Generated Architecture (Joomla 5/6 Standard)

Regardless of the generator version used, the resulting code strictly follows modern Joomla standards:

### 1. Services (`/services/provider.php`)
The "heart" of the extension. Uses Joomla's **Dependency Injection Container** to register the Dispatcher, the Helper, and the extension itself.

### 2. Dispatcher (`/src/Dispatcher/Dispatcher.php`)
Replaces the old main module file. It is the controller that decides what data to load and which layout to display.

### 3. Helper Factory (`/src/Helper/`)
Auxiliary functions (database queries, data processing) are organized into Helper classes that use native Joomla **Traits**.

### 4. Web Asset Manager (`/tmpl/default.php`)
Display uses the new Joomla Asset Manager. CSS and JS are registered and loaded intelligently.

### 5. PSR-4 Namespaces
All code is organized into Namespaces, ensuring compatibility with the Joomla autoloader.

&copy; 2024-2026 Joomla Extension Generator. Created to raise the standard of development in the Joomla community.
