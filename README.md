# Design's Favorites

A local gallery for the design team to share and browse their favorite reference images, screenshots, and inspiration — organized by category with a filter bar.

---

## How to run

Open a terminal in this folder and start a local server:

```bash
python3 -m http.server 8080
```

Then open **http://localhost:8080** in your browser.

> **Why a server?** The gallery loads your `config.js` files via `<script>` tags, which requires a local HTTP server rather than opening `index.html` directly as a file.

---

## Adding your category

### 1. Create your folder

Add a folder for your images inside `images/`:

```
images/
  your-name-or-theme/     ← create this
    config.js             ← create this (see below)
    photo1.jpg
    screenshot.png
    ...
```

Folder names should be lowercase, no spaces (use hyphens): `color-theory`, `type-specimens`, `motion-refs`.

---

### 2. Create your `config.js`

Inside your folder, create a file called `config.js`. Copy this template and fill in your details:

```js
window.GALLERY_CATEGORIES = window.GALLERY_CATEGORIES || [];
window.GALLERY_CATEGORIES.push({
  folder: 'your-folder-name',   // must match the folder you created
  label:  'Your Label',         // displayed on the filter pill
  color:  '#f472b6',            // pill color — any CSS hex color
});
```

Images are discovered automatically — just drop files into your folder and refresh. No need to list them anywhere.

Pick any color you like for your pill. Some suggestions:
`#f472b6` pink · `#818cf8` indigo · `#34d399` emerald · `#fb923c` orange · `#38bdf8` sky · `#a78bfa` violet · `#facc15` yellow

---

### 3. Register your script in `index.html`

Open `index.html` and find the section marked **CATEGORY SCRIPTS**. Add one line for your folder:

```html
<script src="images/your-folder-name/config.js"></script>
```

It looks like this in the file:

```html
<!-- ═══ CATEGORY SCRIPTS ═══ -->
<script src="images/mikes-refs/config.js"></script>
<script src="images/sarahs-picks/config.js"></script>
<!-- add yours here ↓ -->
<script src="images/your-folder-name/config.js"></script>
<!-- ─── end category scripts ─── -->
```

Each designer only touches their own line — this keeps git conflicts to a minimum.

---

### 4. Refresh the browser

Your category pill appears and images are discovered automatically from the folder. If something looks wrong:

- Check the folder name in `config.js` matches the actual folder name exactly
- Make sure you're running via `python3 -m http.server` (not opening the file directly) — auto-discovery requires a server
- Open the browser console for any load errors

---

## Folder structure reference

```
designs-favorites/
  index.html              ← gallery app (only add your <script> line here)
  README.md               ← this file
  images/
    your-folder/
      config.js           ← your pill settings + image list (edit freely)
      photo1.jpg
      photo2.png
    another-designers-folder/
      config.js
      ...
```

---

## Example `config.js`

```js
window.GALLERY_CATEGORIES = window.GALLERY_CATEGORIES || [];
window.GALLERY_CATEGORIES.push({
  folder: 'motion-refs',
  label:  'Motion Refs',
  color:  '#38bdf8',
});
```

Drop any image files into `images/motion-refs/` and they'll show up automatically on refresh.
