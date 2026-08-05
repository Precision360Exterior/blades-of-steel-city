# Blades of Steel City

Website for the Blades of Steel City oil & gas charity hockey tournament.
Started by and powered by NexTier, a Patterson-UTI company.

**Live site:** https://bladesofsteelcity.github.io

| Event | Where | When |
|---|---|---|
| Blades of Steel City 2026 | Printscape Arena at Southpointe, Canonsburg, PA | Thursday, November 12, 2026 |
| Twig & Puck 2027 | Odessa, TX | February 2027 (tentative) |

Contact: bladesofsteelcity@gmail.com

---

## How to edit the website

The entire site is one file: **`index.html`**. All styling and scripts are
inside it. There is no build step. Commit a change and it goes live in about
a minute.

### Editing wording in the browser

1. Click **`index.html`** in the file list above.
2. Click the pencil icon (Edit this file).
3. Find the text you want to change and type over it.
4. Scroll down, write a short note like "updated sponsorship copy", and click
   **Commit changes**.
5. Wait about a minute, then reload the live site.

### Finding a section

Each section starts with a comment banner. Use `Ctrl+F` / `Cmd+F` in the
editor to jump to one:

| Search for | Section |
|---|---|
| `HERO` | Logo, headline, event date band |
| `STAT BAND` | Money raised / nonprofits / teams numbers |
| `MISSION` | Who We Are, facts list, Compete/Connect/Contribute |
| `EVENTS` | The 2026 Pittsburgh and 2027 Odessa cards |
| `PAST EVENTS / IMPACT` | Where the Money Went donation cards |
| `SCHEDULE` | Run of show and the bracket table |
| `SPONSORSHIP` | The five sponsorship tier cards |
| `SPONSOR LOGO WALL` | Sponsor logos and the Thank You panel |
| `REGISTER` | Registration call to action |
| `FOOTER` | Contact info and links |

### Rules of thumb

- Only change text that sits **between** tags: `<h3>Change this</h3>`.
- Do not delete `<` or `>` characters or anything inside a tag.
- Write `&amp;` instead of a bare `&` in body copy.
- If a change breaks the layout, open the **Commits** tab, find the previous
  commit, and revert it. Nothing is ever permanently lost.

---

## Adding registration and sponsorship links

Scroll to the very bottom of `index.html` and find the `LINKS` block:

```js
const LINKS = {
  player:  "",   // Player Registration
  cup:     "",   // The Cup — $8,000
  crispy:  "",   // Crispy Sweaters — $4,000
  biscuit: "",   // Biscuit Backer — $2,500
  clean:   "",   // Clean Sheet — $1,000
  icing:   ""    // Icing (Bar/Food) — $500
};
```

Paste each payment URL between the quotation marks:

```js
  player:  "https://your-payment-page.com/player",
```

Any button whose link is still empty stays greyed out and unclickable, so
you can add them one at a time without breaking anything.

---

## Adding sponsor logos

See `assets/sponsors/HOW-TO-ADD-A-LOGO.txt` for full instructions.

Short version: put the logo file in `assets/sponsors/`, then in the sponsor
logo wall section replace one `Your Logo Here` line with:

```html
<a href="https://sponsor-website.com" target="_blank" rel="noopener">
  <img src="assets/sponsors/sponsor-name.png" alt="Sponsor Name">
</a>
```

Tiles are white, so dark and color logos both look clean. Transparent PNG
is best.

---

## Using a custom domain

GitHub Pages supports custom domains for free with automatic HTTPS. If you
buy something like `bladesofsteelcity.org`:

1. At your domain registrar, add a `CNAME` record for `www` pointing to
   `precision360exterior.github.io`.
2. In this repo, go to **Settings → Pages → Custom domain**, enter the
   domain, and save.
3. Check **Enforce HTTPS** once the check mark appears.

---

## Files

```
index.html                              the entire website
assets/logo.jpg                         full logo, used in the hero
assets/logo.webp                        compressed logo
assets/logo-mark.webp                   small logo for the header and footer
assets/favicon.png                      browser tab icon
assets/sponsors/                         put sponsor logos here
```
