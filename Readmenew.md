# PDF Overlay Project

## Overview
This project provides a solution for overlaying PDFs with data extracted from Excel files. The project includes Python scripts for processing Excel files, reading encrypted PDFs, and performing overlay operations.

## Features
- Extract data from Excel files and overlay onto PDFs.
- Supports encrypted PDF files.
- Automatically builds an executable for Windows using GitHub Actions.

## System Requirements

### Development Environment:
- **Operating System**: Windows 10/11, Ubuntu 20.04 or later.
- **Python Version**: Python 3.10 or later.
- **Required Libraries**:
  - `openpyxl` for handling Excel files.
  - `msoffcrypto-tool` for processing encrypted Microsoft Office files.

### Build Environment:
- **Operating System**: Windows 10/11, Windows Server 2019 (or equivalent).
- **Software**:
  - Git
  - GitHub Actions (for automated builds)
  - Python 3.10+
  - PyInstaller (for creating the executable)

## Installation Instructions

### Setting Up the Development Environment (Windows):

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/YOUR_ORG/PDF_OVERLAY.git
   cd PDF_OVERLAY

2. **Install Python**: Download and install Python 3.10+ from python.org.
3. **Install Required Dependencies**:Open a terminal (Command Prompt or PowerShell) and run:
   ```bash
    pip install openpyxl
    pip install git+https://github.com/nolze/msoffcrypto-tool.git

4. **Run the Application**:To run the application from the terminal:
   ```bash
    python src/main.py

### Building an Executable (.exe) for Windows:
To build the executable, we use GitHub Actions for automation.
1. **GitHub Action Workflow**: A workflow is set up to build the project into an .exe using **PyInstaller**. You can find the workflow file at .github/workflows/build.yml.

