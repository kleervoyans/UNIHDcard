# UniHD Card (Flipper Zero app)

UniHD Card is a **native Flipper Zero NFC app** for reading Uni Heidelberg DESFire student cards.

## Features

- Read card live (`Read card`) via `NfcProtocolMfDesfire`.
- Load and inspect saved `.nfc` card dumps (`Load dump`).
- Show parsed technical fields on-device:
  - UID
  - ATQA / SAK
  - ATS (TL/T0 + optional TA1/TB1/TC1)
  - DESFire HW/SW version bytes
  - DESFire application count
  - Free-memory availability (+ byte count when provided by the card)

## Build and install

```bash
ufbt
ufbt launch
```

## App Catalog readiness

This app is packaged as an external Flipper app (`application.fam`) with metadata, category, description, and version fields set.

## Important note about student data

Uni Heidelberg card semantics like **student number, purse balance, and transaction logs** depend on DESFire application/file layout and access rights (keys/permissions).

This codebase currently provides robust **reader/inspector** functionality for DESFire metadata and NFC dumps. If you want semantic decoding next, capture sample cards and map AIDs/files first, then extend `helpers/unihd_card.c` with UniHD-specific parsing.
