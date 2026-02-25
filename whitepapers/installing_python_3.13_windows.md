# Installing Python 3.13 on Windows

**1. Download**
Go to [python.org/downloads](https://www.python.org/downloads/) and download the **Python 3.13 Windows installer** (64-bit recommended).

**2. Run the Installer**
- Open the downloaded `.exe` file
- ✅ Check **"Add python.exe to PATH"** (important!)
- Click **"Install Now"**

**3. Verify Installation**
Open **Command Prompt** (`Win + R` → type `cmd`) and run:
```
python --version
```
You should see `Python 3.13.x`. Also verify pip:
```
pip --version
```

---

**That's it!** You're ready to run Python scripts with `python yourscript.py` or open an interactive shell by typing `python`.

> **Tip:** If `python` isn't recognized after install, restart your terminal or PC so the PATH change takes effect.
