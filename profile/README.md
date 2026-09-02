# warefeats

Benchmarks for developer tools, with the runs attached.

Most tool comparisons are written by someone selling one of the tools. The rest quote a number with no machine, no versions, and no workload behind it. So I run them myself, on my own hardware, with a runner you can read. Every result page names the rig, pins the versions, and publishes every pass. No sponsor. Nobody on the site pays me. Where I've committed code to a project under test, the page says so up top.

Read the results at [warefeats.com](https://warefeats.com).

## How this org is laid out

One repo per benchmark. The site only renders what the runners produce.

- [warefeats.com](https://github.com/warefeats/warefeats.com): the publication site. Each runner is pinned by commit in `web/data/registry.json`; a new pin is a new page.
- [js-linter-tools](https://github.com/warefeats/js-linter-tools): ESLint vs Biome, run against ESLint's own source.
- [http-caching-proxies](https://github.com/warefeats/http-caching-proxies): Varnish vs Vinyl vs NGINX serving HLS. Docker Compose, three topologies.
- [js-bundlers](https://github.com/warefeats/js-bundlers): Vite vs esbuild vs tsup, cold production builds of zod's source.
- [kv-stores](https://github.com/warefeats/kv-stores): Redis vs Valkey vs Dragonfly under memtier. The first cloud rig: two Graviton3 boxes in a placement group.
- [vector-tile-servers](https://github.com/warefeats/vector-tile-servers): Martin vs Tegola vs BBOX vs pg_tileserv vs TiPg vs ldproxy, all cutting tiles from the same PostGIS. The 2024 Rechsteiner thesis re-run on current releases and a Berlin OSM extract anyone can download.
- [workflows](https://github.com/warefeats/workflows): the shared CI workflow the rest of these call.

## Rerun one yourself

Clone the runner, `bun install`, `just smoke` to check the rig, then the full run (each README names the recipe). The JSON it writes is the shape the site reads; the runner's README says how it lands in the catalog.

If your numbers disagree with mine, open an issue on that runner with your machine and your samples. Corrections go up as new runs. The old one stays, with a note.

I'm John Carmack (the Rust and TypeScript one, not the Doom one).
