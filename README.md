# Tablets Professional V13

This version keeps the Supabase data model unchanged and provides the cleaner card-based UI.

IMPORTANT:
- The app has no login.
- Supabase Project URL is already filled in.
- Replace `PASTE_YOUR_PUBLISHABLE_KEY_HERE` in index.html with your existing browser-safe Publishable key before deploying.
- Do NOT run any database SQL. The database already contains your tablets.

V13 fixes:
- Clean single UI, no duplicate old table/stats.
- All tablets load from Supabase.
- Father/Mother only in the For filter, not on cards.
- Category filter works and shows category-specific tablets.
- Status filter works.
- Search works.
- Status can be toggled by tapping the status pill.
- Quantity uses +/- controls.
- Inline Edit changes only name and dose/strength.
- Mark all received button.
- Copy To-Buy List and WhatsApp.


## Quantity/status behavior

- Press **+**: quantity increases and the medicine automatically becomes **Need to Buy**.
- Press **−**: quantity decreases; status remains unchanged until the status pill is tapped.
- Tap **Need to Buy** -> **In stock**: quantity automatically resets to **1 Sheet**.
- Tap **In stock** -> **Need to Buy**: status changes, quantity is kept as-is.
- **Mark all received**: all Need to Buy medicines become In-stock and reset to 1 Sheet.


## V15 visual polish

- Custom medicine app icon.
- Matching teal app branding.
- Branded splash/loading screen.
- iPhone safe-area support for notches/Dynamic Island and Home Indicator.
- Apple touch icon metadata for a cleaner Home Screen installation.


## V16 safety improvement

Deleting a tablet now shows a medicine-specific confirmation dialog:
"Delete \"Tablet Name Dose\" from your medicine list? This cannot be undone."

The delete action is only performed after confirmation.


## V17 bulk action safety

The bulk action is now labeled **✅ All received**.
When pressed, it asks for confirmation with the exact number of medicines that will be changed and warns that their quantities will reset to 1 Sheet.


## V18 features

- Dedicated **To Buy** screen with its own medicine list.
- To Buy count shown in the tab.
- Copy List directly from the To Buy screen.
- Order preview showing the exact WhatsApp-style medicine list.
- Light / Dark / System appearance modes.
- Appearance choice is saved on the device.


## V24 critical JavaScript fix

The V18 build contained a stale `clearTop` event binding even though the top-right button had been renamed to `themeButton`. That caused a JavaScript error before `loadData()` and the theme handlers could run. V24 removes that stale binding, restores the known-working shared `APP_USER_ID` medicine query, embeds the supplied Supabase publishable key, and bumps the service-worker cache.
