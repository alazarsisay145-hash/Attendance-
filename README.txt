WORKDAY OFFLINE ATTENDANCE & PAYROLL — VERSION 4

WHAT THIS VERSION DOES
- Runs as a single-device offline-first app.
- Registers employees with a unique permanent QR ID.
- Stores each employee's daily wage.
- Generates QR cards without loading an online QR library.
- Scans QR codes using the browser's built-in BarcodeDetector where available.
- Shows the employee name after a recognized scan.
- Records one attendance entry per employee per local calendar date.
- Blocks duplicate scans for the same employee/date.
- Stores the wage rate on each attendance record, so later wage changes do not rewrite historical earnings.
- Calculates payroll as the sum of the wage saved on each attendance day.
- Tracks payments separately and calculates outstanding balances.
- Exports attendance/payroll CSV files and full JSON backups.
- Supports restoring a JSON backup.

IMPORTANT LIMITATIONS
1. DATA BELONGS TO THIS ONE DEVICE + THIS BROWSER PROFILE.
   Do not expect another phone to see these employees or records. QR cards contain only an ID, not the employee's name or wage. The app looks up the ID in this device's local employee register.
2. OFFLINE CAMERA ACCESS:
   First publish/open the app on an HTTPS host (for example GitHub Pages) while online. Open it once so the service worker can cache the app. Camera access also requires HTTPS, browser permission, and a browser that supports BarcodeDetector. If not supported, use manual QR ID entry.
3. INSTALLATION:
   GitHub Pages hosting is only needed to deliver the app shell and service worker on first load/update. After the app is cached, it can work offline on that same device.
4. BACKUPS:
   Browser storage can be cleared by the user, browser settings, or device cleanup. Download and keep JSON backups regularly. Test restoring a backup before using real payroll.
5. QR VALIDATION:
   QR encoding is local and uses short IDs. Test a printed card with a second QR scanner before issuing cards to staff.
6. ATTENDANCE POLICY:
   This app records the scan date based on the device's local date/time. Keep the device clock correct. It is not tamper-proof and does not prove that the employee personally presented the card.
7. PAYROLL:
   Earnings are calculated from attendance records. Payments are manual entries. This is not tax, pension, overtime, leave, or statutory payroll software.

GITHUB PAGES QUICK SETUP
- Create a public repository.
- Upload the CONTENTS of this folder to the repository root (index.html must be at root).
- Settings > Pages > Deploy from a branch > main > /(root) > Save.
- Open the GitHub Pages URL in Chrome while online.
- Wait for it to load, then reload once. Add to Home screen if desired.
- Test QR generation, camera support, duplicate rejection, wage calculation and backup/restore.
- Turn off Wi-Fi and mobile data and test again on the same device.

SAMPLE PAYROLL
Daily wage 100 ETB × 12 recorded attendance days = 1,200 ETB earned.
If 500 ETB is recorded as paid, outstanding balance = 700 ETB.
