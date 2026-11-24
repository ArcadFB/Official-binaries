# Official binaries

Unofficial convenience mirror of unmodified upstream Helm and kubectl binaries for **macOS Apple Silicon (darwin/arm64)**. Not affiliated with Helm or Kubernetes. These are macOS binaries, not Linux ARM64 binaries.

## Downloads

[Release and downloadable assets](https://github.com/ArcadFB/Official-binaries/releases/tag/helm-v4.3.2_kubectl-v1.37.2)

- Helm **v4.3.2** (Helm 4 major version).
- kubectl **v1.37.2**. Choose a kubectl version compatible with your cluster; supported skew is within one minor version of the API server.
- `SHA256SUMS` contains SHA-256 checksums of the downloadable binaries.

## Integrity and provenance

Downloaded from `get.helm.sh` and `dl.k8s.io`. The Helm archive and kubectl binary were checked against upstream SHA-256 checksums before publication. Helm was extracted without modification. Both binary headers were checked as Mach-O ARM64. Full source URLs, versions, sizes and binary hashes are recorded in [provenance.json](provenance.json).

Checksums establish agreement with the downloaded upstream checksums; this is not an independent signature or malware audit. Execution on macOS has not been tested by this mirror. Follow your organization's software approval and scanning process.

## Install after downloading and approval

Download both binaries and `SHA256SUMS` into the same directory, then on your Mac:

```sh
shasum -a 256 -c SHA256SUMS
mkdir -p "$HOME/.local/bin"
install -m 755 helm-v4.3.2-darwin-arm64 "$HOME/.local/bin/helm"
install -m 755 kubectl-v1.37.2-darwin-arm64 "$HOME/.local/bin/kubectl"
"$HOME/.local/bin/helm" version
"$HOME/.local/bin/kubectl" version --client
```

Add `$HOME/.local/bin` to PATH if needed. Do not bypass macOS or workplace security controls.

## Licenses

Both upstream projects are distributed under Apache License 2.0. See [Helm license](LICENSE-helm) and [Kubernetes license](LICENSE-kubernetes). Upstream sources: https://github.com/helm/helm and https://github.com/kubernetes/kubernetes.
