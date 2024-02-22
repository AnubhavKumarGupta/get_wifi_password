# Wi-Fi Password Extractor

This Python script allows you to extract and display Wi-Fi passwords saved on your Windows system. It utilizes the `netsh` command-line utility to retrieve the saved Wi-Fi profiles and their corresponding passwords.

## How to Use
1. Run the Python script.
2. The script will extract the saved Wi-Fi profiles and their passwords.
3. It will then display the Wi-Fi profile names along with their passwords.

## Features
- Extracts and displays saved Wi-Fi passwords on a Windows system.
- Utilizes the `netsh` command-line utility to retrieve Wi-Fi profiles and passwords.
- Provides a simple and convenient way to access saved Wi-Fi passwords.

## Requirements
- Python installed on your system.
- Windows operating system.

## Running the Script
Simply run the Python script using the Python interpreter:

```bash
python wifi_password_extractor.py
```

## Note
- This script requires administrative privileges to retrieve Wi-Fi passwords.
- It uses the `subprocess` module to execute shell commands and parse the output.
- The extracted passwords are displayed along with the corresponding Wi-Fi profile names.


---

**Author:** Anubhav Kumar Gupta
