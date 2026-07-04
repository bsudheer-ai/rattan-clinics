# Dr. Rattan's Clinics — Digital Business Card

One webpage, two clinics. Patients scan a QR (or tap a WhatsApp link), land on this page, and save the right contact in one tap.

## Clinic Structure

| Clinic | Services | Location |
|--------|----------|----------|
| Dr. Rattan's Physiotherapy Clinic | Physiotherapy | 155 B, Rajguru Nagar, Ludhiana 141012 |
| Dr. Rattan's Physiodent Clinic | Dental + Physiotherapy | #5, Street No. 2, Bhai Harnam Singh Nagar, Sua Road Threekey, Ludhiana 142028 |

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | The landing page (self-contained: no build step, no dependencies) |
| `physio-clinic.vcf` | Contact card for Dr. Inderpreet Singh at Physiotherapy Clinic (Rajguru Nagar) |
| `physiodent-dental.vcf` | Contact card for Dr. Rupinder Kaur at Physiodent Clinic (Sua Road) |
| `physiodent-physio.vcf` | Contact card for Dr. Inderpreet Singh at Physiodent Clinic (Sua Road) |
| `physiodent-both.vcf` | Both doctors at Physiodent Clinic in one file |
| `qr-dental.png` / `qr-physio.png` | DEMO QR codes — regenerate after hosting |

## Go-live steps

1. **Confirm the details.** Names, spellings, phone numbers, and addresses — verify every digit before publishing. Edit `index.html` and the `.vcf` files with any corrections (they're plain text).

2. **Host it.** Already deployed via GitHub Pages at the repo URL. Or use:
   - **Netlify Drop** (netlify.com/drop): drag this whole folder into the browser.
   - Optional: buy a domain like `rattanclinics.in` (~₹500–800/yr) and point it at the site.

3. **Regenerate the QR codes with the real URL.** The included QRs point to a placeholder. Once you have the live URL:

   ```python
   import qrcode
   qrcode.make("https://YOUR-REAL-URL/#physio-clinic").save("qr-physio.png")
   qrcode.make("https://YOUR-REAL-URL/#physiodent-clinic").save("qr-physiodent.png")
   ```

   The `#physio-clinic` / `#physiodent-clinic` anchors scroll the page to the right clinic.

4. **Distribute:**
   - Print the QR on the next batch of physical cards
   - Put a printed QR at each clinic's reception desk
   - Save the link as a WhatsApp quick-reply
   - Add the link to each clinic's Google Business Profile

## Why the QR contains a URL, not the contacts

The QR only encodes the web address. All contact data lives on the page and in the `.vcf` files — so if a phone number changes, you edit the file and re-upload. **The printed QR never needs to change.**

## To-verify checklist

- [ ] Dr. Rupinder Kaur — name spelling, B.D.S. title
- [ ] Dental phone: +91 99885 06438
- [ ] Dr. Inderpreet Singh — name spelling
- [ ] Physio phone: +91 99882 48113
- [ ] Physiotherapy Clinic address: 155 B, Rajguru Nagar, Ludhiana 141012
- [ ] Physiodent Clinic address: #5, Street No. 2, Bhai Harnam Singh Nagar, Sua Road Threekey, Opp. Jagjit Nagar, Ludhiana 142028
- [ ] Which numbers are on WhatsApp (the wa.me buttons assume the mobile numbers above)
