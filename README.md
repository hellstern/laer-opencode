# Lær OpenCode

Et dansk kursus i AI-agenter med [OpenCode](https://opencode.ai/), skrevet til deltagere, der ikke er udviklere. Lavet af [Azanta](https://azanta.ai) til deltagerne på vores AI-forløb.

**Læs kurset her: https://hellstern.github.io/laer-opencode/**

## Om repoet

Hjemmesiden er bygget med MkDocs Material. Hver gang der pushes til `main`, bygger en GitHub Action siden og lægger den på GitHub Pages.

- `mkdocs.yml`: menu og opsætning
- `docs/`: alle sider i Markdown
- `docs/stylesheets/azanta.css`: Azanta-farver
- `docs/filer/`: filer til download

Se siden lokalt:

```
pip install mkdocs-material
mkdocs serve
```

## Kilder

Indholdet bygger på den officielle dokumentation på https://opencode.ai/docs/ (OpenCode 2, november 2026). Opbygningen er inspireret af https://learnopencode.com/en/, men teksterne er skrevet fra bunden.
