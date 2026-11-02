# Poltsiko Begie

A personal expense tracker with a Basque interface and a dark theme. It keeps two ledgers, money covered by someone else and own spending, and splits shared expenses between named people.

## Contents

- [Features](#features)
- [How it is built](#how-it-is-built)
- [Data model](#data-model)
- [Running your own copy](#running-your-own-copy)
- [Security](#security)

## Features

- A dual ledger with monthly views.
- A debts tab that splits shared expenses between named people and tracks who owes what.
- Installable on a phone, with offline use and sync on reconnect.

## How it is built

- A single `index.html` with inline HTML, CSS and JavaScript. No framework, no build step.
- Firebase Cloud Firestore and Hosting, loaded from the Firebase CDN.
- A network-first service worker, a web manifest and icons, so it installs on a phone.

## Data model

- Expenses, people and settings are stored as Firestore collections; the app is a single page with no build step.

## Running your own copy

This repository ships with placeholder Firebase settings, so it needs your own project.

1. Create a Firebase project and enable Cloud Firestore.
2. Replace the `YOUR_...` values in the `firebaseConfig` object in `index.html` with your project values.
3. Run `firebase use --add`, then `firebase deploy`.

The investment tracker (Begi Luze) was built to share this app Firebase project and sends its cash movements here.

## Security

`firestore.rules` allows reads and writes without sign-in. That matches how the app was used, by one person and a few friends on a private link, and it is not suitable for anything sensitive on a public address. Add Firebase Authentication and owner-only rules before storing real data.

## Licence

MIT. See [LICENSE](LICENSE).
