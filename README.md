# Python-TOTP-Generator

This repository contains a Python script for generating Time-based One-Time Passwords (TOTP). These passwords are utilized in two-factor authentication, a security process in which the user provides two different authentication factors to verify themselves to better protect both the user's credentials and the resources the user can access.

## How it Works

The script takes secret keys from a JSON file and generates the corresponding TOTP for each key. The secrets are Base32 encoded strings that are unique to each application (for example, Google, LastPass, JumpCloud, etc.)

## Installation

To install and run the script, follow the steps below:

1. **Clone the repository:**

    ```
    git clone https://github.com/username/python-totp-generator.git
    ```

    **Note:** Replace `username` with your actual GitHub username.

2. **Navigate to the cloned directory:**

    ```
    cd python-totp-generator
    ```

3. **Make the script executable:**

    ```
    chmod +x totp_generator.py
    ```

## Usage

1. **Create a JSON file named `secrets.json`**: This file should contain your secret keys in the following format:

    ```json
    {
        "application1":"<Your_Base32_Secret>",
        "application2":"<Your_Base32_Secret>",
        "application3":"<Your_Base32_Secret>",
        "application4":"<Your_Base32_Secret>"
    }
    ```

    Replace `application1`, `application2`, etc., with the names of your applications and `<Your_Base32_Secret>` with the corresponding secret key.

2. **Run the script**: Use Python to run the script with the command:

    ```
    python3 totp_generator.py
    ```

    The script will then generate a six-digit TOTP for each of your applications and print them in the terminal.

## Security Measures

In the interest of security, this script has been designed to avoid storing or displaying sensitive information unnecessarily. Specifically:

- The script only reads from the secrets file when run, and does not write or store the secret keys anywhere else.
- The TOTP codes generated are not stored and are only displayed in the console output.

**NOTE:** Always ensure your `secrets.json` file is stored securely and not shared or committed to public repositories as it contains sensitive information.

## Dependencies

- Python 3
- HMAC (Python built-in)
- hashlib (Python built-in)
- time (Python built-in)
- base64 (Python built-in)
- struct (Python built-in)
- json (Python built-in)
- os (Python built-in)
