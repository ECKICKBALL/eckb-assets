# ECKB Assets

Shared brand asset library for **Emerald City Kickball — Melbourne**. Intended
as an organisation repo so email templates, socials and web can all reference
one canonical copy of the logos instead of passing PNGs around in chat.

## The green

Take the green from the **logo**, not the national brand guide — they disagree,
and the logo is what people actually see on jerseys, socials and Eventbrite.

| Token | Hex | On white | On black | Use for |
|---|---|---|---|---|
| `--eckb-green` | `#54B848` | 2.52:1 **FAIL** | 8.33:1 AAA | Fills, backgrounds, logo lockups |
| `--eckb-green-mid` | `#3F8A36` | 4.29:1 AA-large | 4.90:1 AA | Large headings on white |
| `--eckb-green-dark` | `#2A5C24` | 7.91:1 AAA | 2.65:1 FAIL | **Body text on white** |
| `--eckb-green-deep` | `#152D12` | 14.83:1 AAA | 1.42:1 FAIL | High-emphasis text |

`#54B848` was sampled from the 6422×4302 master logo, where it accounts for 37%
of all opaque pixels. Contrast figures are measured (WCAG 2.1), not estimated.

**The trap:** the primary green fails contrast on white at 2.52:1. It looks
right and is legally the brand colour, but it is not readable as body text on a
white email background. Use `#2A5C24` for text and keep `#54B848` for fills.

Tokens are in [brand/tokens.css](brand/tokens.css) and
[brand/tokens.json](brand/tokens.json).

## Logos

`logos/master/` holds full-resolution originals pulled from the Melbourne Google
Drive (`Branding/Logos/`). `logos/email/` holds derivatives at 600px (email
header) and 200px (signature / footer).

| File | Use |
|---|---|
| `eckb-melbourne-logo` | Primary lockup |
| `eckb-melbourne-logo-reversed` | On dark backgrounds |
| `eckb-melbourne-logo-white-text` | On photography / mid-tone backgrounds |
| `eckb-circle-logo` | Avatars, social profile images, favicons |
| `kickball-mark-1`, `kickball-mark-2` | Standalone ball marks |

The vector master (`Emerald City Kickball Melbourne logos.ai`, 17MB) stays in
Drive — it is not committed here. Fonts and team logos likewise still live in
Drive under `Branding/`.

## Using in email

Email clients do not support CSS custom properties. Inline the hex directly:

```html
<td style="background:#54B848;padding:24px;text-align:center;">
  <img src="https://<host>/logos/email/eckb-melbourne-logo-reversed-600.png"
       width="300" alt="Emerald City Kickball Melbourne" style="display:block;margin:0 auto;">
</td>
<td style="color:#2A5C24;font-size:16px;">Body copy uses the dark green, not the primary.</td>
```

Always set `width` and `alt`. Serve images over HTTPS from a stable host —
Google Drive links are not reliable as email image sources.

## Source of truth

- Logos and fonts: Melbourne Google Drive → `Branding/`
- Tone, usage, national rules: "Emerald City Kickball Marketing & Communication
  Guidelines" (Google Doc) — authoritative for everything **except** the green.
