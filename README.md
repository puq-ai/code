<h1 align="center">
  <img src="assets/puq-code-hero-2.svg" alt="puq code: From first prompt to final diff. A coding agent that lives in your terminal. puqqy by a campfire on a moonlit lake in pixel art; up to 42% cheaper than Claude Code in our tests." width="100%">
  <br>
  puq code
</h1>

<p align="center">
  <b>A coding agent that lives in your terminal.</b><br>
  Same hidden tests passed as Claude Code, <b>up to 42% cheaper</b> in our tests.
</p>

<p align="center">
  <a href="https://github.com/puq-ai/code/releases"><img alt="Latest release" src="https://img.shields.io/github/v/release/puq-ai/code?style=flat-square&label=release&color=4C8DFF&labelColor=141413"></a>
  <img alt="Platforms" src="https://img.shields.io/badge/macOS%20%C2%B7%20Linux-arm64%20%7C%20x64-4C8DFF?style=flat-square&labelColor=141413">
  <a href="LICENSE"><img alt="MIT license" src="https://img.shields.io/badge/license-MIT-B0AEA5?style=flat-square&labelColor=141413"></a>
</p>

<p align="center">
  <a href="#install">Install</a> ·
  <a href="#cost-in-our-tests">Savings</a> ·
  <a href="#what-puq-code-does">What it does</a> ·
  <a href="#meet-puqqy">Meet puqqy</a> ·
  <a href="#channels">Channels</a> ·
  <a href="#license-and-attribution">License</a>
</p>

---

## Install

```sh
curl -fsSL https://github.com/puq-ai/code/releases/download/channels/install.sh | sh
```

Then run `puq` inside any project. On first launch, sign in with your **puq** account
(`/login puq`, a puq.ai token) — `/model` then lists every tool-capable model puq serves.

| Platform | Architectures      |
| -------- | ------------------ |
| macOS    | arm64, x64         |
| Linux    | x64, arm64 (glibc) |

This repository holds the release binaries only; CI publishes them, there is no source code here.

## Cost in our tests

Every hidden test passed on both sides. Cost at catalog API prices, both tools at high effort.
Against our everyday Claude Code setup (skills and plugins loaded), puq code cost up to 42% less
(Oct 1, one session per model). Against a clean setup, 3 sessions per cell (Oct 7):

| Model      | Task      | puq code | Claude Code | Saving   |
| ---------- | --------- | -------: | ----------: | -------: |
| Sonnet 5.5 | 4 turns   |   $0.174 |      $0.215 |  **19%** |
| Sonnet 5.5 | 12 turns  |   $1.591 |      $1.797 |  **11%** |
| Opus 5.5   | 12 turns  |   $3.285 |      $3.581 |   **8%** |
| Opus 5.5   | 4 turns   |   $0.479 |      $0.487 |   **2%** |

With each tool's default effort puq cost more on Oct 7; v1.0.5 changed how `auto` picks effort and
we haven't re-run that comparison yet.

## What puq code does

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>Works in your codebase</h3>
      Reads, searches and edits files, runs shell commands, and talks to your language servers
      (LSP) for definitions, references and diagnostics.
    </td>
    <td width="50%" valign="top">
      <h3>Wastes fewer calls</h3>
      A leaner prompt, ranked code-search hits and trimmed tool output; <b>up to 42% cheaper</b>
      than Claude Code in our tests. The status line can show each turn's cost.
    </td>
  </tr>
  <tr>
    <td valign="top">
      <h3>Extensible</h3>
      MCP servers, subagents for parallel work, web search, and Claude Code
      <code>settings.json</code> hooks work as-is.
    </td>
    <td valign="top">
      <h3>Safe to experiment</h3>
      File checkpoints with <code>/undo</code> and <code>/redo</code>, plus an OS-level sandbox
      for shell commands.
    </td>
  </tr>
  <tr>
    <td valign="top">
      <h3>Scriptable</h3>
      Structured output with <code>--output-schema</code> for CI, and
      <code>puq github install</code> to wire puq into a repository's workflows.
    </td>
    <td valign="top">
      <h3>Keeps itself current</h3>
      Checks its channel on launch and every 6 hours, verifies the SHA-256, and switches over
      on the next start. Or run <code>puq update</code>.
    </td>
  </tr>
</table>

## Meet puqqy

<img align="right" src="assets/puqqy.svg" alt="puqqy" width="96">

puqqy is puq code's pixel companion. It doesn't write code; it keeps you company while code gets
written. It hops onto the splash screen, then lives in the status line and takes every small win
and every stumble a little personally: a cheer when a turn finishes, a tear when one fails, a nap
when you've stepped away.

<p align="center">
  <img src="assets/puqqy-moods.svg" alt="puqqy's moods: idle, blink, done, error, asleep" width="100%">
</p>

It's off by default. Bring it in:

```sh
puq config set display.mascot on       # animated, with reactions
puq config set display.mascot static   # shown, no animation
```

or pick **Settings → Appearance → Mascot**.

## Channels

| Channel          | Install                                                                                 | Gets                                       |
| ---------------- | --------------------------------------------------------------------------------------- | ------------------------------------------ |
| stable (default) | `curl -fsSL https://github.com/puq-ai/code/releases/download/channels/install.sh \| sh` | versions that spent about a week on latest |
| latest           | `… \| sh -s -- latest`                                                                  | every release as it ships                  |

Switch an existing install: `puq config set update.channel latest` (or `stable`). Switching never
downgrades; you stay on your version until the channel passes it. GitHub's "Latest" badge marks
the current stable release.

<details>
<summary><b>Uninstall</b></summary>

```sh
rm ~/.local/bin/puq && rm -rf ~/.local/share/puq ~/.puq-code
```

This also deletes your settings and session history under `~/.puq-code`.

</details>

## License and attribution

puq code is released under the MIT license — see [LICENSE](LICENSE).

puq code is derived from [oh-my-pi](https://github.com/can1357/oh-my-pi) ("OMP"), which is also MIT-licensed.
`LICENSE` keeps OMP's original copyright lines (Mario Zechner; Can Bölük; Stencil Labs, Inc.) next to puq's. Third-party
components bundled into the binaries and their licenses are listed in
[THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt). Both files are also embedded in every binary: `puq --license`.

<p align="center"><img src="assets/puqqy.svg" alt="" width="40"></p>
