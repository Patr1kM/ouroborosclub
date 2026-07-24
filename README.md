# ouroborosclub
# Ouroboros Club — Member Card Reference

How to update a member's card. The physical NFC card never needs to be
touched again once written — it only stores a URL (e.g.
`yourusername.github.io/m/001/`). Everything shown on tap is pulled live
from GitHub, so editing the file is all you ever need to do.

---

## A. Upload the profile photo

1. Go to the repo → open the member's folder (e.g. `m/001`)
2. **Add file → Upload files**
3. Drag in the cropped, square photo
4. Rename it exactly **`photo.jpg`** before committing
   (if it's a `.png`, either rename the extension to match or update the
   `<img src="photo.jpg">` line in that member's HTML to `photo.png`)
5. **Commit changes**

## B. Upload the club logo

Only needs to be done once — every member page already points to it.

1. Go to the **root** of the repo (not inside any `m/00X` folder)
2. **Add file → Upload files**
3. Drag in the square, transparent-background logo
4. Rename it exactly **`logo.png`**
5. **Commit changes**

## C. Edit the text fields

1. Open `m/001/index.html` (or the relevant member folder)
2. Click the **pencil icon** (top right) to edit
3. Overwrite the text between the tags — do not touch the tags themselves

| Field | Find this line | Edit |
|---|---|---|
| First name | `<div class="first-name">Patrik</div>` | replace name |
| Last name | `<div class="last-name">[Surname]</div>` | replace surname |
| Location | `<div class="location">Bangkok · Hungarian / Swiss-Italian</div>` | replace text |
| Summary | `<div class="summary"> Founder of Blue Sail Branding... </div>` | replace both sentences |
| Role | 1st `<div class="detail-value">Founder of Blue Sail Branding</div>` | replace |
| Field | 2nd `<div class="detail-value">Luxury Hospitality</div>` | replace |
| Frequented Countries | 3rd `<div class="detail-value">Hungary · Thailand · Switzerland</div>` | replace |

4. **Commit changes**

## D. Edit the contact links

Only the `href=` value matters functionally — the visible label is cosmetic.

| Contact | Find | Replace with |
|---|---|---|
| LinkedIn | `href="https://linkedin.com/in/yourhandle"` | real LinkedIn URL |
| Instagram | `href="https://instagram.com/yourhandle"` | real Instagram URL |
| Email | `href="mailto:you@email.com"` | `mailto:` + real email, no spaces |
| Phone | `href="tel:+66000000000"` | `tel:` + number with country code, no spaces/dashes |
| WhatsApp | `href="https://wa.me/66000000000"` | `https://wa.me/` + number, no `+`, no spaces |

To remove a contact method entirely: delete the whole block, from
`<a class="social-link">` to its closing `</a>`, for that item. The grid
reflows automatically.

## E. Verify

Wait 30–60 seconds after committing (GitHub Pages redeploy time), then
open `yourusername.github.io/m/001/` in an **incognito/private tab**
(avoids seeing a cached old version) and confirm everything landed
before relying on the physical card.

---

## Adding a brand new member

1. Open an existing finished member's folder (e.g. `m/001/index.html`) → copy the full file
2. Create a new file at `m/002/index.html` → paste it in
3. Edit per sections C and D above
4. Upload their `photo.jpg` into `m/002/`
5. Commit → live at `yourusername.github.io/m/002/`
6. Write that exact URL to a blank NFC card via NFC Tools (Write → Add Record → URL)

## Notes

- Commit photo, logo, text, and links as **separate commits** when
  working on a new member — makes it obvious which change broke
  anything, if something does.
- The logo only needs uploading once, ever, at the repo root.
- Changing content never requires rewriting the physical card. Only
  rewrite a card if the folder path itself changes.
