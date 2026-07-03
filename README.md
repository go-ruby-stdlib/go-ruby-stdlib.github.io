# go-ruby-stdlib.github.io

The ecosystem **portal** for [go-ruby-stdlib](https://github.com/go-ruby-stdlib) —
the pure-Go, CGO-free reimplementation of the MRI-compatible Ruby standard
library. Served at <https://go-ruby-stdlib.github.io> and built with
[Hugo](https://gohugo.io).

It is a single page (custom `layouts/index.html`) that indexes **every module**
in the ecosystem, grouped by wave. The module list is data-driven from
`[[params.modules]]` in `hugo.toml`; each entry renders a card with its Ruby
module, one-line description, and three uniform links:

- repo — `https://github.com/go-ruby-<name>/<name>`
- landing — `https://go-ruby-<name>.github.io/`
- docs — `https://go-ruby-<name>.github.io/docs/`

The top call-to-action points at the aggregate module
[`github.com/go-ruby-stdlib/stdlib`](https://github.com/go-ruby-stdlib/stdlib),
which pulls the whole tower with one import.

`.github/workflows/deploy-pages.yml` builds the landing with Hugo and deploys it
to GitHub Pages (Actions source) on every push to `main`.

## Local preview

```bash
hugo server      # http://localhost:1313
```
