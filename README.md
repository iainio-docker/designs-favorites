# Design's Favorites

A shared gallery for the design team. Filter by category, drop in images, refresh.

**To run:** `cd` into this folder, then:
```bash
python3 -m http.server 8080
```
Open **http://localhost:8080**

---

## 1. Add a category

Create a folder under `images/` and add a `config.js` inside it:

```
images/
  your-category/
    config.js
```

`config.js` contents:
```js
window.GALLERY_CATEGORIES = window.GALLERY_CATEGORIES || [];
window.GALLERY_CATEGORIES.push({
  folder: 'your-category',
  label:  'Your Label',
  color:  '#f472b6',
});
```

Then register it in `index.html` by adding one line in the **CATEGORY SCRIPTS** section:
```html
<script src="images/your-category/config.js"></script>
```

Pill color suggestions: `#f472b6` pink · `#818cf8` indigo · `#34d399` emerald · `#fb923c` orange · `#38bdf8` sky · `#a78bfa` violet

---

## 2. Add images

Drop image files directly into your category folder:

```
images/
  your-category/
    config.js
    photo1.jpg
    screenshot.png
```

<<<<<<< HEAD
Refresh the browser and they'll appear automatically. Supported formats: jpg, png, gif, webp, avif, svg.
=======
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

## Goal 2: Add images to gallery

Add 1 image to each category through a PR with verified commits using a local sandbox. Add a table for "Design/Eng partners".

### Pairings

Designers, please schedule a 30min sync to partner with your eng colleague to setup sbx verified commits.

| Designer | Eng Partner |
|----------|-------------|
| @mia | @rob.murray |
| @rcjsuen | @patrick.port |
| @sean | @Manu |
| @javier.alonso | @ndeloof |
| @Prashant Khanchandani | @ignasi |

By the next studio in 2 weeks, we'll spend a few minutes reviewing all the photos we merged into the project.

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
>>>>>>> 5cf02aa (docs: add Goal 2 section with Design/Eng pairings)
