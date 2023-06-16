# Project Description: Chrome Password Decryptor

The "Chrome Password Decryptor" project is a Python script that allows users to decrypt and retrieve saved passwords from the Google Chrome browser on a Windows system. This project utilizes various libraries and methods to access and decrypt the encrypted password data stored in the Chrome browser's local database.

The script makes use of the following libraries and modules:

```
    os: Provides functions for interacting with the operating system.
    json: Handles JSON data parsing and manipulation.
    base64: Performs Base64 encoding and decoding operations.
    sqlite3: Enables database connectivity and SQL query execution.
    win32crypt: Offers functions for decrypting Windows-specific protected data.
    Crypto.Cipher: Provides encryption and decryption capabilities using various algorithms.
```

To decrypt the Chrome passwords, the script follows the following steps:

1. Retrieves the encryption key from the Chrome "Local State" file, which is encoded in Base64 format and encrypted with the user's credentials.
2. Decrypts the encryption key using the CryptUnprotectData function from the win32crypt module, obtaining the original session key.
3. Copies the Chrome browser's local database file to another location to avoid potential locking issues.
4. Connects to the copied database file using the sqlite3 module.
5. Executes a SQL query to retrieve the relevant password data from the "logins" table.
6. Decrypts each password using the AES encryption algorithm, utilizing the obtained encryption key.
7. Displays the decrypted password, along with the associated username, URL, creation date, and last usage date.

The project provides a command-line interface where users can execute the script and retrieve their decrypted Chrome passwords. Additionally, it prompts users to enter their name and greets them after displaying the decrypted password information.

## Installation

8. Clone the repository or download the script file (chrome_password_decryptor.py) to your local machine.
9. Ensure that you have Python 3.x installed on your system.
10. Install the required modules by executing the following command:

```
    pip install pypiwin32 pycryptodomex
```

11. Once the installation is complete, you are ready to use the "Chrome Password Decryptor" script.

## Usage

12. Open a command-line interface (e.g., Command Prompt, Terminal).
13. Navigate to the directory where the script (chrome_password_decryptor.py) is located using the cd command.
14. Run the script by executing the following command:

```
    python chrome_password_decryptor.py
```

15. The script will display the decrypted passwords along with the associated username, URL, creation date, and last usage date, if available.
16. The script may prompt you to enter your name. Type your name and press Enter to proceed.
17. After displaying the decrypted password information, the script execution will be completed.

The "Chrome Password Decryptor" project offers a convenient way to retrieve saved passwords from the Google Chrome browser. It can be helpful in situations where users need to recover their passwords or transfer them to another password management tool securely.

Feel free to explore the code and adapt it to suit your specific requirements or integrate it into your own projects.
