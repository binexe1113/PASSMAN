    # PASSMAN
    #### Video Demo: https://www.youtube.com/watch?v=onKPhPLwAc8
    #### Description:
# Passman - Secure Password Manager

## Overview
Passman is a password manager that leverages cryptography and comma-separated values (CSV) to provide secure password management. It allows users to:
- Generate a strong password.
- Restore a stored password.
- Add an existing password.
- View all stored passwords and their associated usernames/sites.

All operations require authentication via a master key, ensuring that only authorized users can access stored credentials.

## Features
- **Master Key Authentication:**
  - On first use, the user sets a master key, which is securely stored.
  - On subsequent runs, the program prompts for this master key before granting access.
  - After five failed attempts, the system deletes both the master key file and stored passwords.
  
- **Secure Password Generation:**
  - Uses Python's `string` and `random` libraries to generate passwords with uppercase, lowercase, digits, and punctuation.
  - Allows users to specify password length.
  - Provides an option to store the generated password securely.
  
- **Password Storage:**
  - Encrypts passwords using the `cryptography` library (Fernet encryption).
  - Stores encryption keys securely using the `keyring` library.
  - Saves encrypted passwords in a CSV file for easy retrieval.

- **Password Retrieval:**
  - Users can retrieve a password by searching for its associated username or site.
  - The `tabulate` library is used to present stored credentials in a well-formatted table.

- **Adding Existing Passwords:**
  - Users can manually add passwords to the system.
  - Passwords are encrypted before being stored in the CSV file.

- **Viewing Stored Passwords:**
  - Decrypts and displays all stored passwords with their associated usernames/sites in a clean, tabulated format.

## Security Measures
- **Hidden Input:**
  - All password prompts use the `getpass` library to prevent password exposure.
- **Encryption & Secure Storage:**
  - Uses `cryptography` (Fernet) for encryption.
  - Stores encryption keys securely via `keyring`.
- **Automatic Deletion on Failed Authentication:**
  - After five incorrect master key attempts, the system deletes stored passwords for security.

## Technologies Used
- Python standard libraries: `getpass`, `random`, `csv`, `os`, `string`
- Third-party libraries: `cryptography`, `keyring`, `tabulate`

## Installation & Usage
1. **Install Dependencies:**
   ```sh
   pip install cryptography keyring tabulate
   ```
2. **Run the Program:**
   ```sh
   python passman.py
   ```
3. **Follow On-Screen Instructions:**
   - Set up a master key on the first run.
   - Use the menu to generate, store, retrieve, or manage passwords.

## License
Passman is an open-source project. Feel free to modify and contribute!

---
Developed with security in mind to help users manage passwords safely. 🚀

