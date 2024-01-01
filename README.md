# asdf-trippy

![CI](https://github.com/fartbagxp/asdf-trippy/workflows/CI/badge.svg)
![Lint](https://github.com/fartbagxp/asdf-trippy/workflows/Lint/badge.svg)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://choosealicense.com/licenses/mit/)
[![Doc](https://img.shields.io/badge/Doc-asdf-blue)](https://asdf-vm.com/)

This is a [trippy](https://github.com/fujiapple852/trippy) plugin for the [asdf version manager](https://asdf-vm.com/).

## Usage

- Trippy requires [certain privileges](https://github.com/fujiapple852/trippy#privileges) which we can tailor to [asdf](https://asdf-vm.com/).

### Unix

1: Run as root user via sudo:

```bash
sudo -E `asdf which trip` example.com
```

2: chown trip as the root user and set the setuid bit:

```bash
sudo chown root $(asdf which trip) && sudo chmod +s $(asdf which trip)
```

3: [Linux only] Set the CAP_NET_RAW capability:

```bash
sudo setcap CAP_NET_RAW+p $(asdf which trip)
```

## Issues

- Need to figure out how to map which [binary download](https://github.com/fujiapple852/trippy#binary-asset-download) the user's installation is using.

## Contents

- [Plugin Dependencies](#plugin-dependencies)
- [Install](#install)
- [License](#license)

## Plugin Dependencies

- `curl` - for trippy downloads from upstream releases

## Install

Plugin:

```bash
asdf plugin-add trippy https://github.com/fartbagxp/asdf-trippy
```

trippy:

```bash
# Show all installable versions
asdf list-all trippy

# Install specific version
asdf install trippy latest

# Set a version globally (in your ~/.tool-versions file)
asdf global trippy latest

# Run trippy
trip --version
> trip 0.90.0
[...]
```

## Uninstall

```bash
asdf plugin remove trippy
```

## License

See [LICENSE](LICENSE).
