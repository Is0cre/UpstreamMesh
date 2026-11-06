# UpstreamMesh

Open-source, solar-powered environmental telemetry and disaster communication mesh for flood-prone, infrastructure-limited river basins.

The public site lives in [`index.html`](index.html) and is meant to be served from GitHub Pages at [upstreammesh.org](https://upstreammesh.org/).

## Publish

1. Push this repository to `main` on GitHub.
2. Open **Settings → Pages → Build and deployment**.
3. Set **Source** to **Deploy from a branch**, branch `main`, folder **`/ (root)`**.
4. Under **Custom domain**, enter `upstreammesh.org` and save. Enforce HTTPS after the certificate is issued.

DNS at the registrar:

| Host | Type | Value |
| --- | --- | --- |
| `@` | A | `185.199.108.153` |
| `@` | A | `185.199.109.153` |
| `@` | A | `185.199.110.153` |
| `@` | A | `185.199.111.153` |
| `@` | AAAA | `2606:50c0:8000::153` |
| `@` | AAAA | `2606:50c0:8001::153` |
| `@` | AAAA | `2606:50c0:8002::153` |
| `@` | AAAA | `2606:50c0:8003::153` |
| `www` | CNAME | `Is0cre.github.io` |

GitHub Pages will redirect `www` to the apex once both names resolve. The [`CNAME`](CNAME) file in this repo pins the apex domain.

Do not add a CNAME record on `@`. Apex records are the four A records (and the AAAA records, if the registrar supports them).
