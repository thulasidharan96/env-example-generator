# env-example-generator

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
![HTML5](https://img.shields.io/badge/HTML5-Yes-E34F26?logo=html5&logoColor=white)
![Vanilla JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?logo=javascript&logoColor=111)
![Client-Side](https://img.shields.io/badge/Runtime-Client--Side-2563eb)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero-16a34a)
[![Deploy Pages](https://github.com/thulasidharan96/env-example-generator/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/thulasidharan96/env-example-generator/actions/workflows/deploy-pages.yml)

Privacy-first, client-side `.env` → `.env.example` generator. No backend, no uploads, no dependencies.

## 1. Overview

`env-example-generator` converts `.env` content into a sanitized `.env.example` directly in the browser.

## 2. Why?

Teams often need to share required environment variable keys without sharing secret values.

## 3. Features

- Real-time `.env` → `.env.example` generation
- Optional comment preservation
- Optional placeholder values (`KEY=<KEY>`)
- Supports `export KEY=value` lines
- Copy to clipboard
- Download generated `.env.example`
- Load sample input
- Clear editor
- Line numbers and line counts
- Keyboard shortcuts
- Responsive single-page layout

## 4. Example

Input:

```env
# App
NODE_ENV=production
PORT=3000
export API_KEY=super-secret
EMPTY_VALUE=
```

Output (default mode):

```env
# App
NODE_ENV=
PORT=
export API_KEY=
EMPTY_VALUE=
```

Output (placeholder mode):

```env
# App
NODE_ENV=<NODE_ENV>
PORT=<PORT>
export API_KEY=<API_KEY>
EMPTY_VALUE=<EMPTY_VALUE>
```

## 5. Privacy First

Transformation happens locally in your browser. The app does not upload `.env` content to a server.

## 6. How It Works

The parser reads input line by line, keeps supported structure, and rewrites assignment values to empty strings or placeholders.

## 7. Placeholder Mode

Enable **Use placeholders** to output `<KEY>` values instead of empty values.

## 8. Comment Preservation

Enable **Preserve comments** to keep comment lines (`# ...`) in the generated file.

## 9. Export Syntax

Lines in the form `export KEY=value` are preserved as `export KEY=` (or `export KEY=<KEY>` in placeholder mode).

## 10. Usage

1. Paste your `.env` into the left editor.
2. Toggle **Preserve comments** or **Use placeholders**.
3. Copy or download the generated `.env.example`.

## 11. Zero Dependencies

This project is a single `index.html` file with embedded CSS and JavaScript.

## 12. Technology

- HTML5
- CSS3
- Vanilla JavaScript (no frameworks)

## 13. Supported Input

- Standard `KEY=value` lines
- `export KEY=value` syntax
- Empty values (`KEY=`)
- Empty lines
- Comment lines (`# ...`)

## 14. Limitations

- Intentionally lightweight parser (not a full dotenv parser)
- Lines without `=` are preserved as-is
- Complex shell parsing edge cases are out of scope

## 15. Security Note

The tool helps generate a sanitized `.env.example`, but you should still review output before committing any file.

## 16. Keyboard Shortcuts

- `Ctrl/Cmd + Enter`: regenerate output
- `Ctrl/Cmd + Shift + C`: copy generated output

## 17. Project Structure

```text
env-example-generator/
├── index.html
├── README.md
├── LICENSE
├── .gitignore
└── .github/
    └── workflows/
        └── deploy-pages.yml
```

## 18. Design Philosophy

One problem, one focused solution, minimal moving parts.

## 19. Why Client-Side?

Client-side processing keeps usage simple, fast, and private for common `.env.example` generation workflows.

## 20. Deployment

GitHub Pages (GitHub Actions):

1. Open repository **Settings**.
2. Open **Pages**.
3. Set **Source** to **GitHub Actions** (if not already set).
4. Push to `main`.
5. Wait for the `deploy-pages` workflow to complete.
6. Open: <https://thulasidharan96.github.io/env-example-generator/>

## 21. Development

```bash
git clone https://github.com/thulasidharan96/env-example-generator.git
cd env-example-generator
```

Then open `index.html` in your browser.

No package installation is required.

## 22. Contributing

Small, focused improvements are welcome. Keep the app client-side and dependency-free.

## 23. Roadmap

- Improve parser edge-case handling while staying lightweight
- Add optional screenshot/documentation updates
- Keep accessibility and mobile UX polished

## 24. Privacy Model

- Input stays in browser memory
- No backend processing
- No analytics or third-party input processing
- No remote storage of your `.env` content

## 25. Use Cases

- Create shareable `.env.example` templates
- Standardize onboarding config files
- Remove secret values before sharing env structure

## 26. Who Is This For?

Developers and teams that use `.env` files and want a quick, local conversion utility.

## 27. Project Goals

- Fast local conversion
- Clear output
- Minimal codebase
- Trustworthy privacy model

## 28. Non-Goals

- Full dotenv specification parser
- Secret scanning or security auditing platform
- Backend/cloud processing

## 29. License

MIT License. See [LICENSE](./LICENSE).

## 30. Author

**Thulasidharan S**

## 31. Support

- Open an issue: <https://github.com/thulasidharan96/env-example-generator/issues>
- Discussions and improvements are welcome.

## Screenshot (Future)

A screenshot section is prepared for a future real UI image. No image is referenced yet to avoid broken links.
