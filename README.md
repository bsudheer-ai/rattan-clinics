# Dr. Rattan's Clinics — Digital Business Card

One webpage, two clinics. Patients scan a QR (or tap a WhatsApp link), land on this page, and save the right contact in one tap.

## What's in this folder

| File | Purpose |
|---|---|
| `index.html` | The landing page (self-contained: no build step, no dependencies) |
| `dental.vcf` | Contact card for Dr. Rupinder Kaur (Dental Clinic) |
| `physio.vcf` | Contact card for Dr. Inderpreet Singh (Physiotherapy Clinic) |
| `both.vcf` | Both contacts in one file (used by the "Save both" link) |
| `qr-dental.png` / `qr-physio.png` | DEMO QR codes — point to a placeholder URL, regenerate after hosting |

## Go-live steps (about 15 minutes, free)

1. **Confirm the details.** Names, spellings, phone numbers, and addresses were read from photos of the physical cards — verify every digit before publishing. Edit `index.html` and the `.vcf` files with any corrections (they're plain text).

2. **Host it free.** Easiest options:
   - **Netlify Drop** (netlify.com/drop): drag this whole folder into the browser. Done. You get a URL like `https://something.netlify.app` (you can rename it, e.g. `rattan-clinics.netlify.app`).
   - Or GitHub Pages / Cloudflare Pages if you prefer.
   - Optional: buy a domain like `rattanclinics.in` (~₹500–800/yr) and point it at the site. Nicer for WhatsApp sharing, but not required.

3. **Regenerate the QR codes with the real URL.** The included QRs point to a placeholder. Once you have the live URL, regenerate with any free QR generator, or:

   ```python
   import qrcode
   qrcode.make("https://YOUR-REAL-URL/#dental").save("qr-dental.png")
   qrcode.make("https://YOUR-REAL-URL/#physio").save("qr-physio.png")
   ```

   The `#dental` / `#physio` anchors scroll the page to the right clinic, so each physical card's QR lands patients on "their" doctor first.

4. **Distribute:**
   - Print the QR on the next batch of physical cards (or as a small sticker on existing cards)
   - Put a printed QR at each clinic's reception desk
   - Save the link as a WhatsApp quick-reply so the doctors can send it in one tap
   - Add the link to each clinic's Google Business Profile

## Why the QR contains a URL, not the contacts

The QR only encodes the web address. All contact data lives on the page and in the `.vcf` files — so if a phone number changes, you edit the file and re-upload. **The printed QR never needs to change.**

## To-verify checklist before printing anything

- [ ] Dr. Rupinder Kaur — name spelling, B.D.S. title
- [ ] Dental phone: +91 99885 06438 (and is 99882 48113 also dental, or the physio number?)
- [ ] Physio phone: +91 99882 48113
- [ ] Physio doctor's full name (inferred from email: Dr. Inderpreet Singh)
- [ ] Both addresses
- [ ] Which numbers are on WhatsApp (the wa.me buttons assume the mobile numbers above)
