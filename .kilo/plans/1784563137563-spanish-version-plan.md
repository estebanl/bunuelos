# Spanish Version Implementation Plan

## Goal
Add a complete Spanish language version of "The Golden Bite" website using the duplicate directory approach (Option 1).

## Approach
Create an `es/` subdirectory containing a translated `index.html`. The existing `style.css` and `main.js` are shared via relative paths, and all `assets/` remain at the project root.

## File Structure
```
.
├── index.html          # English (updated with language switcher)
├── style.css           # Shared
├── main.js             # Shared
├── assets/             # Shared
└── es/
    └── index.html      # Spanish translation
```

## Tasks

1. **Create `es/index.html`**
   - Copy `index.html` to `es/index.html`
   - Update `<html lang="en">` to `<html lang="es">`
   - Update `<title>` and `<meta name="description">` to Spanish
   - Translate all visible text content to Spanish
   - Update asset paths: `./assets/...` → `../assets/...`
   - Update shared file paths: `style.css` → `../style.css`, `main.js` → `../main.js`
   - Preserve all section IDs (`home`, `history`, `recipe`, `gallery`, `places`) so anchor links work identically
   - Translate nav link text (Home → Inicio, History → Historia, etc.)
   - Translate all section headings, paragraphs, badges, buttons, list items, place descriptions, and footer text
   - Keep external URLs unchanged (e.g., Google Maps link)

2. **Update English `index.html`**
   - Add language switcher in navbar: `<a href="/es/">Español</a>`
   - Place it as the last item in `.nav-links` or as a separate element

3. **Update Spanish `es/index.html`**
   - Add language switcher in navbar: `<a href="/">English</a>`

4. **Validation**
   - Open `/` and verify English site loads with Spanish switcher link
   - Open `/es/` and verify Spanish site loads with English switcher link
   - Verify all assets (images, videos) load correctly in both versions
   - Verify scroll animations, navbar effects, and smooth scrolling work in Spanish version
   - Verify gallery images and videos display properly with `../` paths
