# Hypha's opam repository

The opam repository of [Hypha Stack](https://hyphatech.io).

Add it once, then install its packages as any other:

```sh
opam repo add hypha https://github.com/hyphatech/opam-repository.git
opam install spindle
```

That adds it to the current switch, ahead of opam's default repository.
`--all-switches --set-default` adds it to every switch, and to every
switch made later. `opam update hypha` fetches releases published since.

## Packages

| Library | Packages |
|---|---|
| [Spindle](https://github.com/hyphatech/spindle): the web framework for modern OCaml | `spindle`, `spindle-http`, `spindle-postgres`, `spindle-sqlite`, `spindle-client`, `spindle-mcp`, `spindle-mcp-client`, `spindle-cli` |
| [Wiretype](https://github.com/hyphatech/wiretype): JSON contracts for modern OCaml | `wiretype`, `ppx_wiretype` |
| [Rowtype](https://github.com/hyphatech/rowtype): SQL queries and migrations for modern OCaml | `rowtype`, `rowtype-postgres`, `rowtype-sqlite`, `rowtype-migrate` |
| [postgres-eio](https://github.com/hyphatech/postgres-eio): the Postgres driver for modern OCaml | `postgres-eio` |
| [Spool](https://github.com/hyphatech/spool): durable jobs for modern OCaml, backed by Postgres | `spool` |
| [solidtype](https://github.com/hyphatech/solidtype): SolidJS for modern OCaml | `solidtype`, `ppx_solidtype`, `solidtype-kobalte`, `solidtype-heroui`, `solidtype-rhp`, `solidtype-internationalized-date` |

## Licence

[CC0 1.0](LICENSE), as ocaml/opam-repository. The libraries themselves are
MIT.
