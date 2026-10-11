# Probabilistic Computing Learning & Research Portal (`share/public/`)

Open-access **MkDocs Material** site for learning **stochastic computing (SC)**, bitstream arithmetic, and **probabilistic / p-bit** hardware.

Live site (after deploy): [https://probabilistic-computing.github.io/public/](https://probabilistic-computing.github.io/public/)

Companion literature map (titles, venues, DOIs, publisher abstracts only): [PC Paper Map](https://probabilistic-computing.github.io/.github/)

## What this folder is (and is not)

| Allowed | Not allowed |
| :--- | :--- |
| Original educational prose, diagrams, and interactive demos | Copyrighted paper PDFs or figure reproductions |
| Bibliographic citations with DOI / IEEE Xplore links | Verbatim abstracts, tables, or substantial text from papers |
| Links to the public org and Paper Map | Links to private lab repos, internal analyses, or work packages |

## Local preview

```bash
cd share/public
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
# http://127.0.0.1:8000
```

## Deploy

This directory is intended to publish as the standalone GitHub repository [`Probabilistic-Computing/public`](https://github.com/Probabilistic-Computing/public) with GitHub Pages via [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml).

## License

Site content: [CC BY 4.0](LICENSE). Cited works remain under their publishers' copyright.
