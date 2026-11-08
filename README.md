# qr-to-code

Text to QR transfer in a single HTML file. Paste any text or code, and it is split into an ordered series of QR codes. Scan them in sequence into a target field with a barcode scanner, then scan one checksum QR to verify nothing was lost.

Meant for locked-down machines where a barcode scanner is the only way to get text in.

## Use it

Open `index.html` in a browser. No build, no server, no network. The QR encoder is vendored as `qrcode.min.js`.

1. Paste the text and set bytes per QR (50 to 2900, default 800) and error correction.
2. Scan the chunks strictly in order.
3. Scan the checksum QR, or paste the received text to compare it with the checksum.

## Notes

- Text is split by bytes and never cuts a multibyte character.
- Lower bytes per QR if the scanner struggles with dense codes. Raise error correction for poor scans, at the cost of capacity.
- The transfer is lossless only if the scanner adds no suffix (such as Enter) between scans. If it does, the checksum check reports extra characters.
