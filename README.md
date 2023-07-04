# get_wifi_password

This code retrieves the Wi-Fi network profiles and their associated passwords on a Windows system using the `netsh` command-line utility. Here's a breakdown of how the code works:

1. The code begins by importing the `subprocess` module, which allows the execution of system commands from within Python.

2. The `netsh wlan show profiles` command is executed using `subprocess.check_output()`. This command retrieves a list of all Wi-Fi profiles stored on the system. The output of the command is captured and stored in the `data` variable.

3. The captured output is then decoded from bytes to a string using the UTF-8 encoding and split into a list of lines using the `split("\n")` method. Each line represents a Wi-Fi profile.

4. A list comprehension is used to iterate over the lines of `data` and extract the profile names. The line `"All User Profile"` is used as a filter to ensure only relevant lines are considered. The extracted profile names are stored in the `profiles` list.

5. A `for` loop is used to iterate over each profile in the `profiles` list.

6. Within the loop, the `netsh wlan show profile <profile_name> key=clear` command is executed for each profile. This command retrieves the specific profile's details, including the Wi-Fi password, if available. The output is captured and stored in the `results` variable.

7. Similar to step 3, the captured output is decoded, split into lines, and stored in the `results` list.

8. Another list comprehension is used to extract the Wi-Fi passwords from the `results` list. The line `"Key Content"` is used as a filter to ensure only relevant lines are considered. The extracted passwords are stored in the `results` list.

9. A `try-except` block is used to handle any potential `IndexError` that might occur if there are no passwords found for a specific profile. If an `IndexError` occurs, an empty string is printed for the profile's password.

10. Finally, the profile names and passwords (or empty strings) are printed in a formatted manner using `print()`.

The code essentially uses the `netsh` command-line utility to gather information about Wi-Fi profiles on a Windows system and extract their associated passwords, if available.


----------------------------------------------------------------------------------------------------------------------------------



UTF-8 (Unicode Transformation Format-8) is an encoding scheme for representing characters in a Unicode character set. It is one of the most widely used character encodings and supports a vast range of characters from various scripts and languages.

Unicode is a standard that assigns a unique number (code point) to every character across different writing systems and symbol sets. UTF-8 is a variable-width encoding, which means that it can represent characters using different numbers of bytes. It uses one to four bytes per character, depending on the Unicode code point.

UTF-8 is backward-compatible with ASCII (American Standard Code for Information Interchange). ASCII characters (with code points from 0 to 127) are represented using a single byte in UTF-8, making it compatible with the ASCII character set.

The advantage of UTF-8 is its ability to represent characters from multiple languages in a compact and efficient manner. It supports internationalization and allows software applications to handle and display text in different languages.

In the provided code, the `.decode("utf-8")` method is used to convert the output of the `subprocess.check_output()` function, which is in bytes, into a string using the UTF-8 encoding. This allows the subsequent manipulation and processing of the retrieved data as human-readable text.
