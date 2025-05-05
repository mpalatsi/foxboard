# Firefox Extension Homepage – Development Plan

## Name: FoxBoard

## 🎯 Goal
Create a custom Firefox extension that overrides the default homepage/new tab and displays a configurable dashboard with:
- Bookmark management (with import support)
- Folder organization
- Icon view
- Dynamic Unsplash backgrounds
- Time and date display
- Settings via a cog icon

---

## 📁 Project Structure

```
foxboard/
│
├── manifest.json
├── background.js
├── newtab.html
├── newtab.js
├── styles/
│   └── newtab.css
├── components/
│   ├── bookmarkGrid.js
│   ├── settingsPanel.js
│   └── unsplashBackground.js
└── assets/
    └── icons/
```

---

## 🚦 Phase 1: Basic Extension Setup

- Create `manifest.json` with:
  - `chrome_url_overrides.newtab`
  - Permissions for bookmarks, storage, tabs
  - Proper icons and metadata
- Load extension into Firefox for testing

---

## 🧩 Phase 2: Bookmark Management

- Use the [Bookmarks API](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks)
- Features:
  - Import existing bookmarks tree on first run
  - Display as icons with site favicons
  - Create folders (drag/drop, or manual)
  - Editable titles, add/remove bookmarks
  - Organize bookmarks into **categories/sections** (e.g., "Work", "Entertainment", "Tools") that can **expand/collapse**
  - Optional: Save custom "Favorites" section separate from synced bookmarks

---

## 🖼️ Phase 3: Dynamic Backgrounds

- Use **Official Unsplash API** (`api.unsplash.com`)
- **Requires user-provided Unsplash Access Key (Client-ID) via settings.**
- Allow:
  - Daily background rotation
  - Manual refresh button
  - Option to choose category (e.g., nature, tech, minimalism)

---

## 🕒 Phase 4: Clock & Date Display

- Display current time (12/24 hr toggle)
- Display full date (e.g., "Saturday, May 4, 2025")
- Optional: Add weather info later using public APIs (e.g., OpenWeatherMap)

---

## ⚙️ Phase 5: Settings Panel

- Accessible via cog icon in corner
- Toggle features:
  - Background category
  - Icon size or layout grid
  - Clock format
  - Show/hide folders
  - Dark/light mode override
- Store preferences in `browser.storage.local`
- Provide button/instructions to help user set the extension page as their Firefox homepage
- Input field for user's Unsplash Access Key (Client-ID)

---

## 🎨 Phase 6: UI/UX Polish

- Responsive layout (desktop-friendly, mobile-style layout optional)
- Animations on folder open/close
- Hover effects for icons
- Optionally allow custom themes (e.g., select background color or blur)

---

## 🧪 Phase 7: Testing & Packaging

- Test across latest Firefox versions
- Ensure:
  - Bookmark permissions are respected
  - Settings persist after reload
  - New tab loads quickly and efficiently
- Package the extension as `.xpi`

---

## 🧠 Suggestions & Enhancements

- ✅ Drag & drop for reordering bookmarks
- 📌 "Pin" bookmarks to top
- 📂 Sync bookmarks with Firefox Sync or offer local-only mode
- 🧭 Built-in quick search bar (optional)
- 🔔 Notifications (e.g., "X bookmarks added recently")
- 🧱 Optional widgets: weather, to-do list, notes
