# Compiler Installation Guide

To enable full code execution and performance testing for all programming languages, you need to install the required compilers:

## Windows Installation

### Python
1. Download from https://www.python.org/downloads/
2. Run the installer and check "Add Python to PATH"
3. Verify: Open PowerShell and run `python --version`

### Node.js (JavaScript)
1. Download from https://nodejs.org/
2. Run the installer
3. Verify: Open PowerShell and run `node --version`

### C++ Compiler (MinGW)
1. **Option 1: Using Chocolatey (Recommended)**
   - Open PowerShell as Administrator
   - Install Chocolatey if not installed: Visit https://chocolatey.org/install
   - Run: `choco install mingw`
   
2. **Option 2: Manual Installation**
   - Download MinGW from https://sourceforge.net/projects/mingw/
   - Install to `C:\MinGW`
   - Add `C:\MinGW\bin` to your system PATH
   
3. Verify: Open new PowerShell and run `g++ --version`

### Java
1. Download JDK from https://www.oracle.com/java/technologies/downloads/
2. Run the installer
3. Add Java bin directory to PATH
4. Verify: Open PowerShell and run `javac --version`

## Linux/Mac Installation

### Python
```bash
# Ubuntu/Debian
sudo apt-get install python3

# Mac
brew install python3
```

### Node.js
```bash
# Ubuntu/Debian
sudo apt-get install nodejs npm

# Mac
brew install node
```

### C++ Compiler
```bash
# Ubuntu/Debian
sudo apt-get install g++

# Mac (Xcode Command Line Tools)
xcode-select --install
```

### Java
```bash
# Ubuntu/Debian
sudo apt-get install openjdk-17-jdk

# Mac
brew install openjdk
```

## Verifying Installation

After installation, restart your terminal and run:
- `python --version` or `python3 --version`
- `node --version`
- `g++ --version`
- `javac --version`

All commands should return version information without errors.

## Troubleshooting

### "command not found" or "not recognized as internal or external command"
- Make sure the compiler is added to your system PATH
- Restart your terminal after installation
- On Windows, you may need to restart your computer

### Code execution still fails
1. Check that the compiler version is compatible
2. Try running a simple test from the command line
3. Check the error message in the CPU & Performance Analysis section for specific issues

## What Works Without Compilers

Even without all compilers installed:
- ✅ Code translation between languages works
- ✅ Complexity analysis works
- ✅ Theoretical performance comparison works
- ❌ Practical CPU performance testing requires the respective compilers
