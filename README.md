# 🍕 Pizza Order (Mon–Fri) WhatsApp Form

Front‑end only, single file. Touch‑friendly spacing. No login. Opens WhatsApp with a drafted order.

## Public Flow
1. See announcement banner and weekday info.
2. Enter **name**, choose **amount of pizza(s)** (1–4), select **day** (Mon–Fri).
3. Optionally add a **note** (e.g., crunchy/no cheese/address).
4. Tap **Send via WhatsApp** → review and send.

## Admin Settings (edit in `index.html`)
At the top of the script, change:
```js
const ORGANIZER_NAME = 'Purcy';
const PHONE_DEFAULT = '59995120536'; // digits only, no +
const ANNOUNCEMENT_DEFAULT = 'ALV pizza special. Delivery 10:30 (make group of 4 if you want)';
const TITLE_DEFAULT = '🍕 Fast Pizza Order (Mon–Fri)';
```
These are not editable by the public.

## Optional: Per‑office Links via URL
You can override fields without editing the file by adding URL params:
- `?ann=Text` → Announcement
- `&title=Text` → Page title
- `&phone=5999XXXXXXX` → Target WhatsApp number
- `&org=Name` → Organizer name

**Example**
```
https://yourdomain.com/index.html?ann=ALV%20special%20Fri%2010%3A30&org=HR%20Team&phone=59991234567&title=🍕%20HR%20Pizza%20Order
```
This lets you clone to other offices using unique links, no code edits.

## Directory
```
pizza-order/
├── index.html
├── README.md
└── images/
    └── teaser.jpg
```

## Notes
- 1 pizza = 8 slices.
- Uses `window.location.href` to open `wa.me` for better mobile behaviour.
- Name is saved locally (`localStorage`) for convenience.
