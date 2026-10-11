# Cryptolg Password Manager

A command-line password manager built in Python, using Fernet symmetric encryption
to store website credentials in a local SQLite database.

## About

Built January 2021 as a learning project to practice symmetric encryption and SQLite
in Python. Lets a single local user store, view, update and delete website logins,
with the stored password encrypted at rest.

## Features

- CLI menu: list websites, add/update/delete an entry, reveal a decrypted password by ID
- Passwords encrypted with `cryptography.fernet.Fernet` before being written to SQLite
- Password strength check via `password_strength`

## Tech Stack

- Python 3, `sqlite3`, `cryptography` (Fernet), `password_strength`, `tqdm`

## Getting Started

```sh
pip install cryptography tqdm password_strength
python3 -c "from cryptography.fernet import Fernet; open('cryptoKey','wb').write(Fernet.generate_key())"
python3 cryptolg.py
```

The database file (`pythonCryptography.db`) and the `cryptoKey` file are created locally
and are gitignored; they are never committed.

## Status

Learning project, not maintained. Security note: this was built as a Python/crypto
exercise, not a production-grade password manager (login check is a plain string
compare, not hashed).

## License

MIT, see [LICENSE](./LICENSE).
