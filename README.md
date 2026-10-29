# qHorus edge software — public distribution mirror

Public release mirror for the [qHorus](https://app.qhorus.io) edge binaries.
**Contains no source code** — only the compiled installers.

- **Agent** / **qHost** — the software a customer installs on a host they
  want validated. Executes BOCs, writes stage markers, reports verdicts.
- **Collector** — an edge relay that lives inside the customer's perimeter.
  Receives syslog from Components (EDR, firewall, SIEM, WAF) and forwards
  batches to the qHorus control plane. The single outbound tunnel for
  everything that cannot reach `api.qhorus.io` directly (ADR 0046).

## Download

Open the qHorus console (<https://app.qhorus.io>) → *qHosts* → **Add qHost**
or *Collectors* → **Add Collector**. The modal exposes one-liner install
commands and direct-download buttons for every supported platform.

Direct release URLs live at
<https://github.com/fusion-shield/qhorus-edge-releases/releases/tag/agents-latest>.
Each asset ships with a sibling `.sha256`. Verify before executing.

## Supported platforms per binary

- `windows-amd64` — MSI installer + raw `.exe`
- `linux-amd64`, `linux-arm64` — `.tar.gz` with the installer README
- `darwin-amd64`, `darwin-arm64` — `.tar.gz` with the installer README

## Rolling release

The `agents-latest` tag is a moving pointer updated by CI (private source
repo) on every change to the edge binaries. The daily
`agents-freshness` guard opens an issue if it stops moving.
