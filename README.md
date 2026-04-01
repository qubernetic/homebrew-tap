<div align="center">

# Qubernetic Homebrew Tap

[![Tap](https://img.shields.io/badge/homebrew-tap-FBB040.svg?logo=homebrew&logoColor=white)](https://brew.sh/)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

Official [Homebrew](https://brew.sh/) tap for [Qubernetic](https://github.com/qubernetic) tools.

</div>

---

## Usage

```bash
brew tap qubernetic/tap
brew install <formula>
```

Or install directly without tapping first:

```bash
brew install qubernetic/tap/<formula>
```

## Available Formulae

| Formula | Description | Repository |
|---------|-------------|------------|
| `copia` | CLI for Copia — source control for industrial automation | [copia-cli](https://github.com/qubernetic/copia-cli) |

## How It Works

Formulae in this tap are **automatically published** by [GoReleaser](https://goreleaser.com/) when a new version is tagged in the source repository. No manual intervention needed.

## Troubleshooting

```bash
# Update the tap to get latest formulae
brew update

# Reinstall a specific version
brew reinstall qubernetic/tap/<formula>

# Check formula info
brew info qubernetic/tap/<formula>
```

## Adding a New Formula

To publish a new tool to this tap, add a `brews` section to your project's `.goreleaser.yml`:

```yaml
brews:
  - repository:
      owner: qubernetic
      name: homebrew-tap
    homepage: "https://github.com/qubernetic/your-project"
    description: "Your tool description"
    license: "MIT"
    install: |
      bin.install "your-binary"
    test: |
      system "#{bin}/your-binary", "--version"
```

The formula will be automatically created/updated on each tagged release.
