<!-- README.md -->
# 🍕 Pizza Order (Mon–Fri) — WhatsApp Form

Front‑end only, single file. Touch‑friendly spacing. Opens WhatsApp with a drafted order.

## Public Flow
1. See announcement banner and weekday info.
2. Enter **name**, choose **amount of pizza(s)** (1–4), select **day** (Mon–Fri).
3. Optionally add a **note** (e.g., crunchy/no cheese/address).
4. Tap **Send via WhatsApp** → review and send.

## Admin Settings
Defaults (inside `<script>`):
```js
const ORGANIZER_NAME = 'Purcy';
const PHONE_DEFAULT = '59995120536';
const ANNOUNCEMENT_DEFAULT = 'ALV pizza special. Delivery 10:30 (make group of 4 if you want)';
const TITLE_DEFAULT = '🍕 Fast Pizza Order (Mon–Fri)';
```

### Per‑office Links (no file edits)
Use URL parameters:
- `?ann=Text` → Announcement banner
- `&title=Text` → Page title
- `&phone=5999XXXXXXX` → WhatsApp number (digits only)
- `&org=Name` → Organizer name

**Example**
```
https://yourdomain.com/index.html?ann=HR%20pizza%20special%20Fri%2010%3A30&org=HR%20Team&phone=59991234567&title=🍕%20HR%20Pizza%20Order
```

### Built‑in Link Builder (admin)
Click **“Customize link (admin)”** (or append `?builder=1`) to open a small form. Fill Title, Organizer, Phone, Announcement → **Generate link** → Copy/Share/Open. This produces a unique URL for each office without touching the code.

## Notes
- 1 pizza = 8 slices.
- Uses `window.location.href` to open `wa.me` for better mobile behaviour.
- Name is saved locally (`localStorage`) for convenience.
- Keep phone numbers as digits only (no `+`).
