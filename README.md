# vardun.com

The www side of vardun.com: one logo, one page. Served by GitHub Pages at
**https://vardun.com**.

The old site (CrucialP cPanel, retired September 2026) was literally a single HTML file
showing `images/vardun3.jpg`, plus a JavaScript redirect for the long-expired
`lzdesigns.info`. That redirect is gone; the logo is kept.

## Email — do not touch the MX records

`vardun.com` runs **Google Workspace**. DNS is at GoDaddy and the mail records there are
correct:

- `MX  @  1  smtp.google.com` (Google's single-MX setup, not a truncated record)
- `TXT @  v=spf1 include:_spf.google.com ...`
- `TXT google._domainkey` — DKIM
- `TXT _dmarc  v=DMARC1; p=quarantine; ...`

Only the `A` / `CNAME` records point at this repo. Changing anything else in that zone
breaks mail.
