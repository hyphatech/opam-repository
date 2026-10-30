# Hypha's opam repository

The opam packages of [Hypha Stack](https://hyphatech.io), components made
to fit together. Add it once, then install them as any other package:

```sh
opam repo add hypha https://github.com/hyphatech/opam-repository.git
opam install spindle
```

That adds it to the current switch, ahead of opam's default repository.
`--all-switches --set-default` adds it to every switch, and to every
switch made later. `opam update hypha` fetches releases published since.

## Packages

| Package | Library |
|---|---|
| `spindle`, `spindle-http`, `spindle-postgres`, `spindle-sqlite`, `spindle-client`, `spindle-mcp`, `spindle-mcp-client`, `spindle-cli` | [Spindle](https://github.com/hyphatech/spindle): an RFC-strict web framework, typed end to end |
| `wiretype`, `ppx_wiretype` | [Wiretype](https://github.com/hyphatech/wiretype): unified JSON contracts, printed as JSON Schema and Zod |
| `rowtype`, `rowtype-postgres`, `rowtype-sqlite`, `rowtype-migrate` | [Rowtype](https://github.com/hyphatech/rowtype): typed SQL queries on Postgres or SQLite, with migrations built in |
| `postgres-eio` | [postgres-eio](https://github.com/hyphatech/postgres-eio): a native Postgres driver |
| `spool` | [Spool](https://github.com/hyphatech/spool): a durable job queue in your own Postgres |
| `solidtype`, `ppx_solidtype`, `solidtype-kobalte`, `solidtype-heroui`, `solidtype-rhp`, `solidtype-internationalized-date` | [solidtype](https://github.com/hyphatech/solidtype): OCaml front ends on Solid, with Kobalte, HeroUI and rhp, compiled by Melange |

## How a release arrives

Publishing a library's GitHub release uploads its source archive to the
release and pushes its opam files here on a `release/` branch. CI lints
them and installs them on OCaml 5.5, then lands them on `main`. A
published version never changes: a mistake is fixed by the next one.

Every file here meets [ocaml/opam-repository's
policies](https://github.com/ocaml/opam-repository/blob/master/governance/policies/README.md).

## Licence

[CC0 1.0](LICENSE), as ocaml/opam-repository. The libraries themselves are
MIT.
