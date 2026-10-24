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

## The design is not here

It comes from the shared Hugo module
[`go-fleettools/landingkit`](https://github.com/go-fleettools/landingkit),
pinned in `go.mod` (Renovate bumps it); `kit.go` keeps `go mod tidy` from
deleting that requirement. `[params.brand]` in `hugo.toml` is read from the logo by
`landingkit brand`. A file under `layouts/partials/` with the name of one of the
kit's would silently override it.
