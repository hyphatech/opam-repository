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

| Library | Packages |
|---|---|
| [Spindle](https://github.com/hyphatech/spindle): an RFC-strict web framework, typed end to end | `spindle`, `spindle-http`, `spindle-postgres`, `spindle-sqlite`, `spindle-client`, `spindle-mcp`, `spindle-mcp-client`, `spindle-cli` |
| [Wiretype](https://github.com/hyphatech/wiretype): unified JSON contracts, printed as JSON Schema and Zod | `wiretype`, `ppx_wiretype` |
| [Rowtype](https://github.com/hyphatech/rowtype): typed SQL queries on Postgres or SQLite, with migrations built in | `rowtype`, `rowtype-postgres`, `rowtype-sqlite`, `rowtype-migrate` |
| [postgres-eio](https://github.com/hyphatech/postgres-eio): a native Postgres driver | `postgres-eio` |
| [Spool](https://github.com/hyphatech/spool): a durable job queue in your own Postgres | `spool` |
| [solidtype](https://github.com/hyphatech/solidtype): OCaml front ends on Solid, with Kobalte, HeroUI and rhp, compiled by Melange | `solidtype`, `ppx_solidtype`, `solidtype-kobalte`, `solidtype-heroui`, `solidtype-rhp`, `solidtype-internationalized-date` |

## Licence

[CC0 1.0](LICENSE), as ocaml/opam-repository. The libraries themselves are
MIT.
