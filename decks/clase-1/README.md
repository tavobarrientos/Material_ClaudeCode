# Clase 1

Built with [Axo](https://github.com/ambystechcom) · **visibility: `internal`**

```bash
npm install
npm run dev      # http://localhost:8000
npm run pdf      # -> clase-1.pdf
```

## Visibility

`npm run build` works, so you can host it behind auth or hand it over on a stick.
**No deploy workflow was scaffolded** — nothing will publish it for you. Keep this repo **private**.

Change it in `axo.config.mjs`. It is not a label; it is what the tooling enforces.

## Structure

```
slides/         one .mdx per slide   ← what you edit
components/     your .axo components (override a built-in by name)
layouts/        your .axo layouts
css/deck.css    this deck's CSS
axo.config.mjs  title, visibility, footer
```

The compiler, the components, the theme and Reveal all live in `@ambystech/axo`.
Upgrade every deck you own with `npm update @ambystech/axo`.
