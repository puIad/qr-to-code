# AGENTS.md

Single-page app, no build step: `index.html` holds the UI and all logic, `qrcode.min.js` is a vendored QR encoder.

- Run it by opening `index.html` in a browser. Keep it dependency-free and offline.
- Text is split by bytes, never in the middle of a multibyte character. A checksum QR verifies the received text.
- Transfer is lossless only if the scanner adds no suffix between scans.
