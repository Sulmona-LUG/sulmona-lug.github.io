# sulmona-lug.github.io

Sito statico del **Sulmona LUG**, generato con [Jekyll](https://jekyllrb.com/) e pubblicato su
GitHub Pages tramite GitHub Actions.

## Sviluppo locale

Richiede Ruby (con Bundler) installato.

```bash
bundle install
bundle exec jekyll serve
```

Il sito sarà disponibile su <http://localhost:4000>.

## Struttura

- `_config.yml` — configurazione del sito (titolo, navigazione, contatti/social in `social:`)
- `_layouts/`, `_includes/` — template della pagina
- `assets/css/style.scss` — foglio di stile
- `_data/eventi.yml` — elenco degli eventi mostrati in [Eventi](/eventi/)
- `*.md` in root — pagine del sito (una per sezione: chi-siamo, eventi, partecipa, faq, contatti)

## Pubblicazione

Il file `.github/workflows/pages.yml` builda ed esegue il deploy automaticamente su GitHub Pages
a ogni push su `main`. Nelle impostazioni del repository, sezione **Settings → Pages**, imposta
la sorgente su **GitHub Actions**.

## Contenuti da personalizzare

- `_config.yml`: chiave `social` (email, Telegram, GitHub, eventuale Mastodon) e `url`.
- `_data/eventi.yml`: prossimi incontri ed eventi.
- `chi-siamo.md`, `index.md`: testi di presentazione del gruppo.
- `assets/images/logo.svg` e `favicon.svg`: sostituisci con il logo reale del gruppo, quando pronto.

## Licenza

Codice del sito distribuito liberamente; i contenuti testuali sono sotto licenza
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.it) salvo diversa indicazione.
