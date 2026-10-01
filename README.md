# puq-code releases

Binary releases of the puq-code coding agent (the `puq` command) for macOS arm64/x64 and Linux x64/arm64 (glibc).

```sh
curl -fsSL https://github.com/puq-ai/code/releases/download/channels/install.sh | sh
```

Releases are published automatically by CI; this repository holds no source code. Versions start at 1.0.0.

## License and attribution

puq-code is released under the MIT license — see [LICENSE](LICENSE).

puq-code is derived from [oh-my-pi](https://github.com/can1357/oh-my-pi) ("OMP"), which is also MIT-licensed.
`LICENSE` keeps OMP's original copyright lines (Mario Zechner; Can Bölük; Stencil Labs, Inc.) next to puq's. Third-party
components bundled into the binaries and their licenses are listed in
[THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt). Both files are also embedded in every binary: `puq --license`.
