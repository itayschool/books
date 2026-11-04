# Books

Static Hebrew-first reading library for GitHub Pages. Upload the contents of this folder to the publishing root of the repository; no build step is required.

## Publish on GitHub Pages

In **Settings → Pages**, choose the branch and folder that contain `index.html`. The app uses relative paths, so it works on a project URL such as `username.github.io/books/`.

```text
index.html
assets/
  css/app.css
  js/app.js
books/
  math1.pdf
  math2a.pdf
  math2b.pdf
  formulas.pdf       (optional reader reference)
  geometry.pdf       (optional reader reference)
wallpapers/
  manifest.json
  ...image files...
icons/
  manifest.json
  ...SVG files...
.nojekyll
```

## Add reference PDFs

Put `formulas.pdf` and/or `geometry.pdf` in `books/`. Their reader buttons show the PDF beside the open book. Only one reference PDF is shown at a time.

## Add preset wallpapers and icons

Put wallpaper files in `wallpapers/` as PNG, JPG/JPEG, or WebP, then list their exact filenames in `wallpapers/manifest.json`:

```json
["blue-grid.webp", "warm-paper.jpg"]
```

Put SVG icon files in `icons/` and list their exact filenames in `icons/manifest.json`:

```json
["calculator.svg", "bookmark.svg"]
```

The app uses each filename (without its extension) as the display name and shows an image preview. Preset files are part of the repository and cannot be removed from the app. Personal wallpapers and SVGs added through Settings are stored in that browser's local IndexedDB and can be removed there.

## Add the built-in math books

Put the PDFs in `books/` with the lowercase filenames shown above. The library discovers them on first visit and stores a browser-local copy. The catalog IDs stay attached to each book when its displayed name changes, so built-in tables of contents continue to work.

## Personal data and files

Reading progress, names, shelves, bookmarks, notes, themes, button settings, deleted books, and imported Word documents are saved in the browser on that device. Deleted books can be restored from Settings. Browser-local images and icons are also kept in IndexedDB. They are not synced between devices. DOCX files are converted to readable HTML locally in the browser; PDF rendering uses PDF.js and DOCX conversion loads the pinned Mammoth browser build only when a Word document is added.

Files committed to a public repository can be downloaded by anyone who can access the repository or site. Only commit documents and images intended to be public.
