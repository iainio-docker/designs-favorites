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

Refresh the browser and they'll appear automatically. Supported formats: jpg, png, gif, webp, avif, svg.
