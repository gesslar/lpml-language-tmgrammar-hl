# @gesslar/lpml-language-tmgrammar-hl

TextMate grammar for **LPML** (LPC Markup Language) syntax highlighting. LPML is a human-friendly data serialization format designed for MUD configuration files that extends JSON5.

Covers the `.lpml` file extension.

## Installation

```bash
npm install @gesslar/lpml-language-tmgrammar-hl
```

## Usage

### Shiki (standalone)

```js
import { createHighlighter } from "shiki";
import lpml from "@gesslar/lpml-language-tmgrammar-hl";

const highlighter = await createHighlighter({
  themes: ["github-dark"],
  langs: [lpml],
});

const html = highlighter.codeToHtml(code, {
  lang: "lpml",
  theme: "github-dark",
});
```

### Astro / Starlight

In `astro.config.mjs`:

```js
import lpml from "@gesslar/lpml-language-tmgrammar-hl";

export default defineConfig({
  markdown: {
    shikiConfig: {
      langs: [lpml],
    },
  },
  // Or, if using Starlight with Expressive Code:
  integrations: [
    starlight({
      expressiveCode: {
        shiki: {
          langs: [lpml],
        },
      },
    }),
  ],
});
```

### VS Code Extension

In your extension's `package.json`:

```json
{
  "contributes": {
    "grammars": [
      {
        "language": "lpml",
        "scopeName": "source.lpml",
        "path": "./node_modules/@gesslar/lpml-language-tmgrammar-hl/lpml.tmLanguage.json"
      }
    ]
  }
}
```

### Direct import

```js
import grammar from "@gesslar/lpml-language-tmgrammar-hl/lpml.tmLanguage.json" with { type: "json" };
```

## Documentation

<https://spec.gesslar.dev/lpml>

## License

`@gesslar/lpml-language-tmgrammar-hl` is released under the [0BSD](LICENSE.txt).
