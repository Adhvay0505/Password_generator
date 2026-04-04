# BashPass

A secure, encrypted password manager written in pure Bash.

## Features

- Full-screen keyboard-driven TUI with arrow-key navigation
- AES-256-CBC encryption with PBKDF2-SHA256 key derivation
- Private temp-file vault handling during unlocked sessions
- Strong master-password policy for new vault creation
- Strong password generation backed by `/dev/urandom`
- Add custom passwords
- Update existing entries
- Search, browse, and delete passwords
- List services
- Copy to clipboard with timed auto-clear (if `pbcopy`, `xclip`, or `xsel` is available)
- Automatic migration for older `BASHPASS_V1` vault headers and plaintext legacy stores

## Requirements

- Bash 4.0+
- OpenSSL
- Linux/Unix

## Quick Install

```bash
curl -sSL -o BashPass https://github.com/Adhvay0505/BashPass/releases/latest/download/BashPass && chmod +x BashPass && ./BashPass
```

## Manual Install

```bash
git clone https://github.com/Adhvay0505/BashPass.git
cd BashPass
chmod +x BashPass
./BashPass
```

## First Run

1. Run `./BashPass`
2. Create a master password
3. Start managing passwords securely

## Backup

Your vault is stored in `password_store.csv.enc` - safe to copy/back up.

## Security

Master password is never stored. During normal use, the decrypted vault is kept in a private temporary file and wiped on exit/signals. Clipboard copies are automatically cleared after a short timeout when supported by the local clipboard tool.
