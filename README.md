# IxD Research Python Project Template

A clean, modern, and mobile-friendly template for creating academic project pages. This template is maintained by the [Fontys University of Applied Sciences' Interaction Design (IxD) Research Group](https://fontys.nl/onderzoek/ontwerpprincipes-en-technologieen-voor-een-digitale-samenleving.htm) to help students and researchers showcase their work effectively.

![A preview of the project page template](./static/images/carousel1.jpg)

## Features

This template includes pre-built sections for common academic project page components:

- **Teaser Video:** A prominent video banner to showcase your project's main outcome.
- **Image & Video Carousels:** Display multiple images and videos in a clean, interactive format.
- **Embedded Content:** Easily embed YouTube videos and PDF posters.
- **BibTeX Citation:** A pre-formatted BibTeX entry to make it easy for others to cite your work.
- **Responsive Design:** Looks great on desktops, tablets, and mobile devices.

## How to Use This Template

Getting started is simple. Follow these steps to create your own project page:

1.  **Create Your Repository:** Click the "**Use this template**" button at the top of this page to create a new repository with a copy of these files.
2.  **Clone Your New Repository:** Clone the repository you just created to your local machine.
3.  **Customize the Content:** Edit the `index.html` file to replace all placeholder content with your own text, images, and videos. Detailed instructions are provided as comments within the HTML file.
4.  **Deploy Your Website:** Deploy your project page using a service like GitHub Pages, Netlify, or Vercel.

## Customization Checklist

To ensure your project page is complete, make sure you update the following in `index.html`:

- [ ] **Metadata:** Fill in the `<meta>` tags in the `<head>` section for SEO and social media previews.
- [ ] **Title & Authors:** Update the project title and author information.
- [ ] **Links:** Replace all placeholder links with your actual URLs (Paper, Code, Supplementary materials, etc.).
- [ ] **Abstract:** Write a compelling abstract for your project.
- [ ] **Visuals:** Replace all placeholder images and videos in the `static/` directory with your own.
- [ ] **BibTeX Citation:** Update the BibTeX entry with your author details and the final URL of your project page.
- [ ] **Favicon:** Replace the default `favicon.ico` in `static/images/` with your own icon.

---

## Getting Started with Python & `uv`

This project is configured to use [`uv`](https://github.com/astral-sh/uv), an extremely fast Python package installer and resolver. It's a modern replacement for `pip` and `venv`.

### 1. Install `uv`

If you don't have `uv` installed, you can install it with:

```bash
# On macOS and Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# On Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 2. Create and Activate the Virtual Environment

A virtual environment is a self-contained directory that contains a specific Python interpreter and its own set of installed packages, isolated from other projects.

To create a virtual environment for this project using `uv`:

```bash
# This will create a .venv directory in your project folder
uv venv
```

To activate it:

```bash
# On macOS and Linux
source .venv/bin/activate

# On Windows (Command Prompt)
.venv\\Scripts\\activate.bat

# On Windows (PowerShell)
.venv\\Scripts\\Activate.ps1
```

You'll know it's active when you see `(.venv)` at the beginning of your terminal prompt.

### 3. Managing Dependencies

This project uses `pyproject.toml` to manage its dependencies.

#### Adding a New Package

To add a new package (e.g., `pandas`), use the `uv add` command. This will add the package to your `pyproject.toml` and install it in your virtual environment.

```bash
uv add pandas
```

#### Installing from `pyproject.toml`

If you've just cloned the repository or pulled new changes that include new dependencies, you need to synchronize your virtual environment. The `uv sync` command installs the exact versions of the dependencies specified in the `uv.lock` file (which is generated from `pyproject.toml`).

```bash
uv sync
```

This ensures that everyone working on the project has the exact same environment.

## Python Project Structure

This repository also includes a professional directory structure to encourage best practices for Python-based research projects.

```
.
├── config/               # Configuration files
├── data/                 # Project data (raw, processed, etc.)
├── docs/                 # Project documentation
├── notebooks/            # Jupyter notebooks for exploration
├── scripts/              # Standalone scripts for automation
├── src/                  # Main source code for the project
│   ├── __init__.py
│   └── main.py
├── tests/                # Tests for the source code
│   └── __init__.py
├── .env.example          # Example environment variables file
├── .gitignore            # Files and directories to ignore in git
├── pyproject.toml        # Project configuration (dependencies, metadata)
└── requirements.txt      # List of project dependencies
```

### Directory Guide

- **`src/`**: This is the heart of your project. All your core Python source code, organized into modules and packages, should live here. The application's main entry point, `main.py`, is located here.

- **`tests/`**: Contains all the tests for your source code. Keeping tests separate from the application logic is a standard practice that makes the codebase cleaner and easier to maintain.

- **`scripts/`**: Holds standalone scripts used for automation and development tasks. These are not part of the core application. Examples include scripts for data processing, database setup, or running experiments.

- **`notebooks/`**: A dedicated place for Jupyter notebooks. Use these for exploratory data analysis, prototyping algorithms, and visualizing results. Keeping them separate from the `src` directory helps maintain a clean project structure.

- **`data/`**: Use this directory to store data files required for your project. You might consider creating subdirectories like `data/raw` for original, untouched data and `data/processed` for cleaned and transformed data.

  > **Note:** Be careful not to commit large data files to Git. Use a `.gitignore` entry or a tool like Git LFS.

- **`docs/`**: All project-related documentation goes here. This can include anything from formal API documentation generated by tools like Sphinx to general project guides and notes.

- **`config/`**: Store configuration files in this directory. Separating configuration from code is a crucial practice that makes it easier to manage settings for different environments (e.g., local development vs. production server) without changing the code.

### File Guide

- **`pyproject.toml`**: The modern, standardized file for configuring your Python project. It's used to define project metadata (like name and version) and manage dependencies. We recommend using a modern package manager like `uv` to work with this file.

- **`requirements.txt`**: This file lists the specific Python packages your project depends on. It can be generated from `pyproject.toml` to lock down dependency versions for reproducible environments.

- **`.env.example`**: A template for the `.env` file. The `.env` file is used to store environment-specific variables like API keys or database credentials. It should **never** be committed to version control. Copy this file to `.env` and fill in your own secrets.

## Acknowledgements

This template was adapted from the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template) by Eliahu Horwitz, which was in turn inspired by the [Nerfies](https://nerfies.github.io/) project page.

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/). You are free to use and adapt this template, but we kindly ask that you provide attribution by linking back to this repository in your site's footer.
