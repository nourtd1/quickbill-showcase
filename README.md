# QuickBill

> A mobile CRM and invoicing app that helps entrepreneurs and WhatsApp/Instagram sellers move from informal to professional invoicing.

[![App Store](https://img.shields.io/badge/App_Store-Download-000000?style=for-the-badge&logo=apple&logoColor=white)]([LIEN_APP_STORE])

**Status:** 🟢 Live on the App Store (Android version in preparation) · 500+ installs · 4.9★
**Origin:** built as my final project for Harvard CS50x.

## Screenshots

<img src="assets/1.png" width="200"> <img src="assets/2.png" width="200"> <img src="assets/3.png" width="200"> <img src="assets/4.png" width="200">

## Features

- Professional invoices and client management in one app
- Works fully offline: create and edit without a connection
- Automatic sync when the connection returns
- On-device receipt scanning with OCR
- AI-assisted invoicing

## Tech stack

React Native · Expo · TypeScript · expo-sqlite · Supabase (PostgreSQL, Row Level Security) · Tesseract.js

## Architecture

```mermaid
flowchart LR
    A[Mobile app] --> B[(Local SQLite)]
    A --> D[On-device OCR]
    B <-->|sync when online| C[(Supabase / PostgreSQL + RLS)]
```

- **Local-first:** all reads and writes hit SQLite, so the app never blocks on the network.
- **Sync engine:** local changes are pushed to Supabase and remote changes pulled when online.
- **Security:** Row Level Security on every table, each user only sees their own data.

## My role

Product design, architecture, full development and App Store release.

> Source code is private. Contact me for a technical walkthrough: nourdevtd@gmail.com
