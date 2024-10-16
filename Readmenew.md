# PDF Overlay Project

## Overview
This project provides a solution for overlaying PDFs with data extracted from Excel files. The project includes Python scripts for processing Excel files, reading encrypted PDFs, and performing overlay operations.

## Features
- Extract data from Excel files and overlay onto PDFs.
- Supports encrypted PDF files.


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

 ## Build Steps.
  - Clone the repository.
  - Install project dependencies:
  - Push changes to GitHub and trigger the build:
  - Add the .yml file in .github/workflows/ directory.
  - Commit the changes and push them to the main or dev branch.
  - GitHub Actions automatically builds the project:
    (The workflow installs dependencies, builds the .exe file using PyInstaller, and uploads it as an            artifact.)
  - Download the executable from the "Actions" tab on GitHub once the build is complete.

## Run the Applicatin.
Users can run the application by double-clicking the downloaded .exe file.

## Contact
For any inquiries or issues, feel free to contact system department.



