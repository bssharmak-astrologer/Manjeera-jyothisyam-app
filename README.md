# శ్రీ మంజీర జ్యోతిష్యాలయం — Combined Digital Tools

A single installable PWA combining both tools for Sri Manjeera Jyothishyalayam, Pithapuram:

- **నక్షత్ర పొంతన (Nakshatra Porutham)** — 36-point Ashtakoota marriage compatibility calculator
- **పద గణితం (Garba Ganitham)** — Vastu site calculation (Purvaka & Binanka Ganitham)

Opening the app shows a home screen with two cards; tapping either takes you into that tool.
A "← Home" link at the top of each tool brings you back.

## What changed in this version

- **Combined into one app, one icon, one install** — instead of two separate PWAs, this is now
  a single app with a home screen to choose between tools.
- **New unifying icon**: a kalasha (sacred pot) — the traditional symbol of a jyothishyalayam
  itself, neutral across both tools (rather than an icon tied to just one of them).
- **Garba Ganitham picker simplified**: S.No is no longer shown — only the padam value (with
  stars for Purvakam, fractions for Binanakam). The result title now reads just "క్షేత్ర పదము ..."
  without the S.No.
- **Manual padam entry added**: below the picker list in Garba Ganitham, you can type any padam
  directly and calculate results for it — useful for padam values not in the original 89/80-row
  reference tables. Purvakam accepts a whole number; Binanakam accepts a decimal (`22.25`), a
  simple fraction (`1/4`), or a mixed number (`22 1/4`).

## Folder structure

```
manjeera-jyotisham/
├── index.html              # both tools in one file (home screen + 2 sub-screens, JS-toggled)
├── manifest.json           # PWA manifest — name "శ్రీ మంజీర జ్యోతిష్యాలయం"
├── sw.js                   # service worker — offline support for the whole app
├── .nojekyll
├── icons/
│   ├── icon-192.png         # new kalasha icon
│   ├── icon-512.png
│   └── apple-touch-icon.png
└── images/
    ├── ganapathi.jpg         # shared letterhead avatar
    ├── dattatreya.jpg        # shared letterhead avatar
    ├── hands-badge.png       # Porutham section badge
    └── mandala-badge.png     # Garba Ganitham section badge
```

## Deploy to GitHub Pages

Same process as before — if you want to **replace** your existing Porutham repo with this
combined app:
1. Delete the old files in that repo (or start a fresh repo, e.g. `manjeera-jyotisham`).
2. Upload everything from this zip, keeping `icons/` and `images/` as real folders (type the
   folder prefix like `images/ganapathi.jpg` into the filename box if GitHub doesn't preserve the
   folder automatically when dragging individual files).
3. **Settings → Pages** → Source: Deploy from a branch → `main` / `/ (root)` → Save.
4. Live in ~1 minute. Reinstall the PWA on your phone (uninstall the old one first, since the
   icon and app name have changed) to pick up the new combined version.

## Data & formulas

Both tools' full datasets (Porutham's 36×36 points matrix, Garba Ganitham's name lists and
89+80 reference entries) are embedded directly in `index.html` as two `const` objects near the
top of the `<script>` block — search for `POROTHAM_DATA` and `GARBA_DATA`.
