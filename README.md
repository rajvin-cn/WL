# WL

# Python Setup and Verification

This assignment demonstrates how to install and verify Python, check the Python version from the terminal, and understand why Python is important for AI and Generative AI development.

---

## 1. Install Python

To install Python:

1. Go to the official website: https://www.python.org/downloads/
2. Download the latest stable version for your operating system (Windows / macOS / Linux).
3. Run the installer.
4. **Important (Windows users):** Make sure to check **"Add Python to PATH"** during installation.
5. Complete the installation and restart your terminal if needed.

### Installation Screenshot

The image below shows the Python installer with the **"Add Python to PATH"** option highlighted — make sure this box is checked before clicking Install Now.

![Python Installer](images/python_installer.png)

---

## 2. Verify Python Installation

After installing Python, open a terminal or command prompt and run:

```bash
python --version
```

### Verification Screenshot

The image below shows the expected terminal output after a successful installation:

![Python Terminal Verification](images/python_terminal.png)

You should see output like `Python 3.x.x`. If you see an error, make sure Python was added to your PATH during installation.

---

## 3. Troubleshooting Common Installation Issues

### "python is not recognized" / "command not found"

**Cause:** Python was not added to your system PATH.

**Fix (Windows):**
1. Search for **"Environment Variables"** in the Start menu.
2. Under *System Variables*, find `Path` and click **Edit**.
3. Add the path to your Python installation, e.g. `C:\Users\YourName\AppData\Local\Programs\Python\Python312\` and the `\Scripts\` subfolder.
4. Click OK, close all terminals, and reopen a new one.

**Fix (macOS/Linux):**
Add the following line to your `~/.bashrc` or `~/.zshrc`:
```bash
export PATH="/usr/local/bin/python3:$PATH"
```
Then run `source ~/.bashrc` (or `source ~/.zshrc`) to reload.

---

### `python` works but `pip` does not

**Cause:** `pip` may not be on PATH, or was not installed.

**Fix:**
```bash
python -m pip install --upgrade pip
```
If that fails on Windows, re-run the installer and select **Modify → check pip**.

---

### Wrong Python version shown

**Cause:** Multiple Python versions are installed and the old one takes priority.

**Fix:** Use the explicit version command:
```bash
python3 --version   # macOS / Linux
py -3 --version     # Windows (Python Launcher)
```
To make Python 3 the default on Linux/macOS, add an alias to your shell config:
```bash
alias python=python3
```

---

### Permission errors on macOS/Linux during install

**Cause:** Insufficient permissions when installing packages.

**Fix:** Never use `sudo pip install`. Instead, install packages for your user only:
```bash
pip install --user <package-name>
```
Or use a virtual environment (recommended):
```bash
python3 -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
pip install <package-name>
```

---

### Installer fails or freezes on Windows

**Cause:** Antivirus software or a previous incomplete installation.

**Fix:**
1. Temporarily disable antivirus during installation.
2. Uninstall any existing Python version via *Add or Remove Programs*.
3. Delete leftover folders in `C:\Users\YourName\AppData\Local\Programs\Python\`.
4. Re-download the installer from python.org and run as **Administrator**.

---

## Why Python is important for AI/GenAI

Python's simple, readable syntax lets developers focus on AI logic rather than complex code. It has the richest ecosystem of AI/ML libraries, including TensorFlow, PyTorch, and Hugging Face. Its strong community support and easy integration with APIs make it the standard choice for building real-world AI applications.

---

## Demo video

Check out the video here:  
[Verifying your Python installation (and why Python matters for AI/GenAI)](https://www.youtube.com/watch?v=brUVsU59mtA)
