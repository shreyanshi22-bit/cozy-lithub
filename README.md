# 📚 LitHub — Personal Digital Library

> *The digital home for your reading soul.*

LitHub is a single-file, browser-based personal book tracker with a charming cardboard bookshelf aesthetic. It lets you catalog your reading life, track progress, write reviews, and share recommendations — all without a backend, all stored locally in your browser.

## Features

**Library Management**
- Add books with title, author, publication year, genre, status, rating, and personal review
- Track reading status across three states: *Read*, *Reading*, and *Want to Read*
- Star ratings (1–5) with live average shown in the header stats bar
- Customizable spine color for each book from a curated earthy palette

**Bookshelf UI**
- Books are rendered as physical spines on a textured cardboard shelf
- Spines animate on hover (lift, tilt, brighten) and open a floating card popup on click
- Up to 10 books per shelf row; additional rows are added automatically
- Decorative emoji stickers (🦋 🍀 🌸 ✨ and more) can be placed anywhere on the shelf and dragged to reposition

**Browsing & Search**
- Filter by status (All / Read / Reading / Want to Read)
- Search by title or author in real time
- Sort by Recency, Rating, or Title (A–Z)

**Book Popup & Share**
- Tap any book spine to open a floating detail card with genre, rating, status badge, and your review
- Share a book recommendation by copying a formatted text snippet to your clipboard

**Account System**
- Create a personal account (username + password, min. 15 characters) stored locally
- Each account has its own independent book library and sticker layout
- Guest mode is fully functional without signing in
- Accounts and data persist across sessions via `localStorage`

**Stats Dashboard**
- Live counters in the header: total books, books read, and average star rating


## Getting Started

LitHub is a self-contained HTML file — no build step, no dependencies to install.

1. Download `index.html` 
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Start adding books

That's it.


## Usage

**Adding a book** — Click **+ Add Book** in the controls bar. Fill in the details, pick a spine color, rate it, and save.

**Viewing a book** — Click any book spine on the shelf to open its detail card. From there you can edit, share, or delete it.

**Stickers** — Click **➕ Add Sticker** on the bookshelf to pick an emoji. Drag stickers anywhere on the shelf to arrange them. They persist between sessions (per account).

**Accounts** — Click **Sign In** in the top-right corner to create or log into an account. Each account gets its own isolated library and shelf layout.


## Project Structure

The entire application lives in a single HTML file:

```
index.html
├── <style>       — All CSS (layout, shelf, animations, modals, responsive)
├── <body>        — HTML markup (header, controls, shelf, modals)
└── <script>      — All JavaScript (account system, book CRUD, stickers, rendering)
```

No external frameworks. No build tools. Fonts are loaded from Google Fonts (Crimson Text, DM Mono).


## Data & Privacy

All data is stored in your browser's `localStorage` under the following keys:

| Key | Contents |
|---|---|
| `lithub_accounts` | Usernames and base64-encoded passwords |
| `booktracker_<username>` | Book library for a logged-in user |
| `booktracker_guest` | Book library for the guest session |
| `shelf_stickers_<username>` | Sticker positions for a logged-in user |
| `shelf_stickers_guest` | Sticker positions for the guest session |

No data is sent to any server. Everything stays in your browser.


## Browser Support

Works in any modern browser that supports CSS custom properties, `localStorage`, and ES6+. No polyfills are included.


## Customization

A few easy things to tweak directly in the file:

- **Spine colors** — Edit the `SPINE_COLORS` array near the top of the `<script>` section
- **Available stickers** — Add or remove emoji `<span>` elements in the `.sticker-palette` div
- **Genre options** — Edit the `<option>` tags inside the `#f-genre` select element
- **Default sample books** — Modify the `sample` array inside `loadBooksForUser()`


## License

This project is open for personal use. Feel free to fork, modify, or self-host it however you like.
