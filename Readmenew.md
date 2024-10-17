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

## Building an Executable (.exe) for Windows:
To build the executable, we use GitHub Actions for automation.
1. **GitHub Action Workflow**: A workflow is set up to build the project into an .exe using **PyInstaller**. You can find the workflow file at .github/workflows/build.yml.

2. **Triggering the Build**:Any push or Pull request to the main branches will trigger the build process.

## How to Access the Built Executable from GitHub Actions   
1. After each successful build on GitHub, an artifact named**python-app-executable** is uploaded.
2. To download the executable:
   - Go to the **Actions** tab in your GitHub repository.
   - Select the latest build run under **Workflows**.
   - At the bottom of the page, under **Artifacts**, you'll find the *python-app-executable*. Download it        and extract the zip file to find your *.exe*.

## Contributing
1. **Create a Branch**: Always create a new branch when working on features or bug fixes.
   ```bash
   git checkout -b feature-branch

2. **Commit Changes**: After making your changes, commit them.
   ```bash
   git add .
   git commit -m "Your detailed commit message"

3. **Push Changes**: Push your branch to the remote repository.
   ```bash
   git checkout -b feature-branch

4. **Submit a Pull Request**: Create a pull request to merge your branch into the *main* branch.

## GitHub Action for Building the Executable
This project includes a GitHub Action that automates the process of building a Windows *.exe* file from the Python scripts. Here's an overview of the workflow:

  - The action is triggered on pushes to the *main* branch, as well as on pull requests.
  - It checks out the code, installs Python 3.10, installs the required dependencies, builds the executable     using **PyInstaller**, and uploads the result as an artifact.

### GitHub Action Workflow   
Here’s the complete GitHub Action *.yml* file used to build the executable:
   ```bash
   name: Build and Package Executable

on:
  push:
    branches:
      - main
      - dev
  pull_request:
    branches:
      - main
      - dev

jobs:
  build:
    runs-on: windows-latest

    steps:
      # Step 1: Checkout the repository code
      - name: Checkout code
        uses: actions/checkout@v3

      # Step 2: Set up Python
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'

      # Step 3: Install dependencies
      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install pyinstaller
          pip install openpyxl
          pip install git+https://github.com/nolze/msoffcrypto-tool.git

      # Step 4: Build the project into an executable
      - name: Build executable
        run: |
          pyinstaller --onefile src/main.py
          dir dist  # Show the output executable directory

      # Step 5: Upload the executable as an artifact
      - name: Upload executable
        uses: actions/upload-artifact@v3
        with:
          name: python-app-executable
          path: dist/main.exe

### Run the Application
