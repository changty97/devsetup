# devsetup

devsetup is a small command-line tool to install and manage GitHub Actions self-hosted runners across multiple directories.

Features
- Install the GitHub Actions runner software into multiple folders
- Create named runner directories from a prefix
- Set runner labels and counts

Installation
Build from source:
```bash
go build -o ds ./cmd/devsetup
```
Or install with `go install`:
```bash
go install ./cmd/devsetup@latest
```

Usage
```bash
ds [flags]
```

Flags (common)
- `-n, --name`: Name or prefix for the runner directory (required)
- `-l, --label`: Runner label (example: `ubuntu-22.04`, `macos-small`)
- `-c, --count`: Number of runner directories to create (default: 1)
- `--token`: Registration token for the runner (optional; can be provided interactively)
- `-h, --help`: Show help

Examples
- Create a single macOS-labeled runner named `runner01`:
```bash
ds -n runner01 -l macos-small
```
- Create three ubuntu runners with prefix `runner`:
```bash
ds -n runner -c 3 -l ubuntu-22.04
```

Notes
- This tool automates installing the runner software only; you must provide a valid registration token when required by GitHub.
- Check the `cmd/devsetup` source for advanced config and environment options.

Contributing
- PRs welcome. Run `go fmt` before submitting.

License
- MIT
