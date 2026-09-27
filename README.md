# Vertex Science Academy — PWA

Standalone offline-first PWA for Vertex Science Academy, Ambajogai. Designed for Class 10 CBSE Board Science students.

## 60-second client handover

1. Open `app.js` and replace `OWNER_KEY_SHA256` with the SHA-256 hash of the academy's private access key.
2. Upload the **contents of this `pwa` folder** to Netlify Drop, Vercel static hosting, cPanel public_html, or any HTTPS static host.
3. Open the HTTPS URL once on Android Chrome and choose **Add to Home screen / Install app**.
4. The PWA caches its core files after first load and can then operate offline.
5. Share the access key only with enrolled students.

## Important authentication note

Because this is a standalone static PWA with no server, a passcode verifier shipped to the browser is not a true secret: a technically skilled user can inspect the JavaScript and recover or replace the client-side verification. The included SHA-256 comparison prevents the plain-text key from being stored in the source, but it is **not equivalent to server-side authentication**.

For high-security owner-controlled access, keep this UI and move verification to a small HTTPS API/database while retaining the same no-email login flow.

## Included features

- Student full name + academy access key login; no email field.
- First-time roll-number enrollment.
- Local profile, chapter mastery, mock-test, slot and activity persistence.
- Physics / Chemistry / Biology chapter mastery.
- 80-mark mock-test analytics and score trajectory chart.
- Ambajogai exam slot reservation.
- Target percentage, dark mode, report preview/print/share.
- JSON import/export backup.
- Offline service worker and installable manifest.
- 192px and 512px launcher icons.

## Deployment

The folder is already deployable as a static site. No build step is required for the shipped bundle.

For a future Tailwind rebuild, `tailwind.config.js` contains the brand configuration. The shipped CSS is dependency-free so the PWA does not depend on a CDN at runtime.
