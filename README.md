# nullpointio Scoop bucket

Scoop manifests for the free, MIT-licensed, single-exe Windows utilities from
[nullpointio](https://github.com/nullpointio). No installer, no runtime, no telemetry.

| App | What it does |
|---|---|
| [Kilobyt](https://github.com/nullpointio/kilobyt) | Makes a photo provably fit a hard upload limit (exact KB + max pixels), fully offline. |
| [Pastebox](https://github.com/nullpointio/pastebox) | Instant, searchable clipboard history. Nothing on disk unless you pin it. |
| [Turn Off Monitor](https://github.com/nullpointio/turnoffmonitor) | One hotkey, monitors off. Tiny tray exe. |

## Install

```powershell
scoop bucket add nullpointio https://github.com/nullpointio/scoop-bucket
scoop install kilobyt
scoop install pastebox
scoop install turnoffmonitor
```

Update later with `scoop update kilobyt` (or `scoop update *`).

## What is in here

```
bucket/
  kilobyt.json
  pastebox.json
  turnoffmonitor.json
```

Each manifest downloads the release `.exe` straight from the project's GitHub
release and pins the SHA-256 published in that release's `SHA256SUMS.txt`.
`checkver` follows the repository's GitHub releases, and `autoupdate` re-reads
`SHA256SUMS.txt` on the next tag, so each manifest is one `scoop update` away
from the next version.

## Trust and verification

- Every hash in `bucket/*.json` was checked against the release asset it points at
  and against the release's `SHA256SUMS.txt`; CI re-checks all three on every push.
- The exes are **unsigned**, so Windows SmartScreen warns on first run
  (`More info` -> `Run anyway`). The hash is the integrity check, not a signature.
- Source for all three apps is MIT and on GitHub; build scripts are in each repo.

## Uninstall

```powershell
scoop uninstall kilobyt pastebox turnoffmonitor
scoop bucket rm nullpointio
```

## License

The manifests in this bucket are MIT. Each application keeps its own MIT license.
