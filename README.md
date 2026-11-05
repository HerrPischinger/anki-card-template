# Anki card template

A clean, readable card template for [Anki](https://apps.ankiweb.net/) with light and dark mode, a red **Important** box, a blue **Mnemonic** box, a collapsible **Bonus** section, and a **Link** button that opens any URL (for example a YouTube video).

**[Live preview →](https://herrpischinger.github.io/anki-card-template/)**

## Features

- Light and dark mode (follows Anki's night mode)
- Optional **Important** box (red) for pitfalls and key facts
- Optional **Mnemonic** box (blue) for memory aids
- Optional **Bonus** section, collapsed until you click the button
- Optional **Link** button in the same style, opening a URL from a field
- Empty optional fields leave no gaps, and the button row hides itself when there are no buttons
- Uses [Atkinson Hyperlegible Next](https://fonts.google.com/specimen/Atkinson+Hyperlegible+Next) with sensible system fallbacks

## Fields

Create a note type with these fields:

| Field | Required | Purpose |
| --- | --- | --- |
| `Vorderseite` | yes | Front of the card (question) |
| `Rückseite` | yes | Back of the card (answer) |
| `Wichtig` | no | Content of the red "Important" box |
| `Eselsbrücke` | no | Content of the blue "Mnemonic" box |
| `Bonus` | no | Extra content, hidden until the Bonus button is clicked |
| `Link` | no | A URL; shows a "Link öffnen" button when filled |

The field names are German. If you rename them, update the `{{...}}` placeholders in the templates to match.

## Installation

1. In Anki, open **Tools → Manage Note Types**, select your note type, and click **Fields** to add the fields above.
2. Click **Cards…** for that note type.
3. Paste the contents of [`templates/front.html`](templates/front.html) into **Front Template**.
4. Paste the contents of [`templates/back.html`](templates/back.html) into **Back Template**.
5. Paste the contents of [`style.css`](style.css) into **Styling**.

## Link button

Put a plain URL in the `Link` field, for example `https://www.youtube.com/watch?v=...`. The template uses `{{text:Link}}`, which strips any HTML Anki may have added, so the `href` stays clean. On desktop the link opens in your default browser.

## Font

*Atkinson Hyperlegible Next* is not a system font. Devices without it fall back to the system font. To get the same look everywhere, place the font file in Anki's media folder and load it with `@font-face` at the top of `style.css`.

## Repository layout

```
.
├── index.html            # live preview (GitHub Pages)
├── style.css             # card styling, also used by the preview
└── templates/
    ├── front.html        # front template
    └── back.html         # back template
```

## License

MIT, see [LICENSE](LICENSE).
