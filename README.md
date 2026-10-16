# manyballoons-web

The documentation site for [ManyBalloons](https://github.com/SrIruma/ManyBalloons).

It's a static site — plain HTML, CSS and JavaScript, no build step. Open
`index.html` and it works.

## Pages

One view with two sections, switched with the sidebar and searchable with the
box in the top bar (press `/` to jump to it):

- **Documentation** — overview, installation, commands, permissions,
  configuration, creating balloons, the animation engine and the placeholder
  tokens.
- **API** — how to use the API, the method reference, the events and the
  downloads.

## API jars

`api/` holds the compiled integration API the docs link to
(`manyballoons-api.jar`, `manyballoons-api-sources.jar` and
`manyballoons-api-javadoc.jar`). Rebuild them from the plugin repo with
`mvn clean package` and copy the three jars from `api/target/` back here.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Serving it over HTTP (rather than opening the file directly) mirrors how it
behaves on Pages.

## Buy link

The "Buy on BuiltByBit" buttons in `index.html` use the placeholder
`{{BUILTBYBIT_URL}}`. Once the resource is published, replace both occurrences
with the real URL.

## BuiltByBit bio

`Bio.txt` holds the BBCode description for the marketplace listing. Keep the
tags as they are and edit only the text between them.

## Editing the docs

Each page is a `<section class="page">` in `index.html`. The sidebar, search
index and page title are all built from the section's `data-group`,
`data-title` and `data-keywords` attributes, so a new section shows up on its
own. Link between pages with a pager anchor carrying `data-goto="<page-id>"`.

## License

MIT for the site content. The ManyBalloons plugin itself is proprietary and is
sold on BuiltByBit.
