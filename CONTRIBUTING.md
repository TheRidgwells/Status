<p align="center">
  <img src="https://global.media.ridgwell.family/logo.png" height="80" alt="The Ridgwell Family">
</p>

# Contributing to Status

Status is the Ridgwell Family's status page, [status.ridgwell.family](https://status.ridgwell.family), built with
[GitHup](https://github.com/StuxGroup/GitHup). To report an outage, open an Issue. Bugs or ideas for the status page
software belong in [StuxGroup/GitHup](https://github.com/StuxGroup/GitHup/issues).

## Local setup

You need Python 3.11+ and nothing else.

```bash
./dev-server.sh [--no-dev-mode] [port]   # or dev-server.bat on Windows
```

## Project conventions

- **What's monitored** lives in `.githup.yml` only. Public family websites only: never the homelab's services.
- **Don't edit `data/`** by hand: GitHup writes it.
- **Releases:** pre-stable Semantic Versioning (`0.x.y`); the first stable release will be the first Date Version
  (`YY.MM.DD`), with no 1.0.0. Update `CHANGELOG.md` (sections in the order Added, Changed, Fixed, Removed,
  Security, Deprecated), bump `VERSION.md`, run `bash tests/version.sh`, then `./commit.sh`.
- Commits use your own git identity.
