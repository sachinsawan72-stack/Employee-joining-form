# Employee Joining Form – Movietime Cinemas

A single-page web version of the Movietime Cinemas employee joining form. It has the same fields as the original PDF, plus a photograph upload and form validation.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole website. HTML, CSS, JavaScript and the logo are all inside this one file. |
| `README.md` | This guide. |

No build step, no dependencies, no backend.

## Features

- **Movietime Cinemas logo** in the header, taken from the original PDF.
- **Photograph upload:** click or tap the PHOTOGRAPH box, choose an image, and a preview shows in the box. "Remove photo" clears it.
- **All fields are mandatory.** Every field is marked with `*`. This includes gender, marital status, the Yes/No document table, previous company details, reporting manager, and the declaration checkbox.
- **Print protection:** "Print / Save as PDF" works only when every field is filled and a photo is uploaded. If anything is missing, empty fields turn red and the page scrolls to the first one. Printing with Ctrl+P also shows only an "incomplete form" message until everything is filled.
- **Same-as-present address** checkbox copies the present address to the permanent address.
- **Signature boxes** (CM/MOD and Employee) are left empty on purpose. They are signed by hand after printing, so they are not mandatory.
- Works on mobile and desktop, with light and dark mode support.

## How to use

1. Open the page and fill every field marked `*`.
2. Upload the employee photograph.
3. Click **Check form** to see what is still missing (optional).
4. Click **Print / Save as PDF**. In the print window, choose "Save as PDF" or a printer.
5. Sign the printed form (CM/MOD and Employee).

**Reset** clears the whole form, including the photo.

## Run locally

Double-click `index.html` to open it in any modern browser (Chrome, Edge, Safari, Firefox).

## Deploy on Vercel

**Option 1: GitHub (recommended)**

1. Create a new GitHub repository, for example `joining-form`.
2. Upload `index.html` (and this README) to the repository.
3. On vercel.com, click **Add New → Project** and import the repository.
4. Keep the Framework Preset as **Other** and click **Deploy**.

**Option 2: Vercel CLI** (needs Node.js)

```bash
cd path/to/this/folder
npx vercel          # first deploy (preview)
npx vercel --prod   # production deploy
```

To use your own domain, open the project on Vercel, go to **Settings → Domains**, and add it.

## Important notes

- **No data is saved or sent anywhere.** The form works only in the user's browser, and the filled form is taken out only through Print / Save as PDF. If you need submissions to go to email, Google Sheets or a database, a backend or form service has to be added.
- **Sensitive data:** the form asks for Aadhar, PAN and bank details. If you add data storage later, protect the page with a login and use HTTPS (Vercel provides HTTPS by default).
- **Print protection is a convenience check.** It runs in the browser, so a technical user can bypass it. Server-side validation is needed for strict enforcement.
- **Fonts:** the page loads the Figtree font from Google Fonts. If it is blocked or offline, the page falls back to the system font and still works.
- **Fresher employees:** Previous Company and Reporting Manager are mandatory. If freshers will use this form, those two sections should be made optional.

## Customizing

All settings are inside `index.html`:

- **Colors:** change the values at the top of the `<style>` block (`--blue`, `--red`, and so on).
- **Make a field optional:** remove the word `required` from that field's `<input>` tag and remove the `*` from its label.
- **Add or remove a field:** copy an existing `<label class="f">…</label>` block and change its label and `name`.
- **Logo:** replace the `src="data:image/jpeg;base64,…"` value in the header's `<img>` tag.

## Credits

Form content and logo: Movietime Cinemas, from the original "Employee Joining Form (Aug 2026)" PDF.
