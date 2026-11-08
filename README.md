# 64 Locks

**Offline deterministic password generator**  
Single HTML file • No accounts • No cloud • No storage of your secrets

64 Locks generates strong, unique site passwords from a master password + optional key file using Argon2id.  
Everything runs entirely in your browser. Nothing is ever sent anywhere.

---

## Why 64 Locks?

Most password managers store your encrypted vault somewhere (even if locally).  
64 Locks stores **nothing**.  

You only need to remember:
1. Your master password
2. (Optional) the location of your key file

The same inputs always produce the same password for a given site.  
Lose the device? Just open the HTML file again on any computer.

### Key Features

- **Fully offline** — works with no internet after the first load (or completely offline if you save the file)
- **Argon2id** — modern memory-hard key derivation (resistant to GPU/ASIC attacks)
- **Optional key file** — adds a second factor you control (any file works)
- **Counter / version** — change the password for a site without changing your master password
- **Self-test suite** — verifies the crypto implementation is working correctly
- **Single file** — easy to audit, backup, and carry on a USB stick
- **No tracking, no analytics, no phone-home**

---

## Quick Start

1. Download `64locks.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge…)
3. (Recommended) Run the **Self-Test** once to confirm everything works
4. Enter:
   - Master password
   - Site / service name (e.g. `example.com`)
   - Optional key file
   - Optional counter (default `1`)
5. Click **Generate**
6. Copy the password

**Tip:** Bookmark the local file or keep a copy on encrypted USB drives.

---

## How It Works (High Level)

- The master password and key file are never stored.
- The derived key is used only to generate the site password and is discarded immediately.
- Same inputs → same output. Always.

This is the same general approach used by tools like LessPass and Spectre, but with modern Argon2id parameters and a focus on extreme simplicity (one self-contained HTML file).

---

## Security Notes & Threat Model

**What 64 Locks protects against:**
- Server breaches (there is no server)
- Cloud provider access
- Database dumps of password managers
- Most remote attackers (nothing leaves your device)

**What it does *not* protect against:**
- Keyloggers / malware on your device
- Someone who obtains both your master password *and* your key file
- Shoulder surfing while you type the master password
- Extremely weak master passwords (use a long passphrase)

**Recommendations:**
- Use a strong, unique master password (or better: a long passphrase)
- Keep the key file on a separate encrypted drive or USB when possible
- Prefer generating passwords of 20+ characters
- Run the built-in self-test after downloading or moving the file

---

## Self-Test

The tool includes a built-in self-test that checks:
- Argon2id implementation
- Deterministic output consistency
- Basic input handling

Run it after every download or when moving the file to a new device.

## License

Licensed under the **Apache License 2.0**.  
See the (LICENSE) file for the full text.

You are free to use, modify, distribute, and even sell derivatives, as long as you include the license and copyright notice.

---

## Disclaimer

This software is provided "as is", without warranty of any kind.  
The authors are not responsible for any loss of data, access, or security incidents resulting from the use of this tool.

Always keep backups of important account recovery methods.  
Test the generator thoroughly before relying on it for critical accounts.

---

## Credits

Built with a focus on simplicity, auditability, and modern cryptography.  
Inspired by the philosophy of LessPass and Spectre.

If you find this useful, consider starring the repository or sharing it with people who care about privacy.
