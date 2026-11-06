<p align="center">
  <img src="https://global.media.ridgwell.family/logo.png" height="80" alt="The Ridgwell Family">
</p>

# Contributing to Ridgwell Status

Ridgwell Status is the Ridgwell Family's status page, [status.ridgwell.family](https://status.ridgwell.family), built with
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
- **Releases:** [Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, plus `-1`, `-2`... for
  later releases the same day). v26.11.06 was the first stable release, and there's no going back to `0.x.y`. Update `CHANGELOG.md` (sections in the order Added, Changed, Fixed, Removed,
  Security, Deprecated), bump `VERSION.md`, run `bash tests/version.sh`, then `./commit.sh` (or `commit.bat`). Work goes on `test`, and reaches `main` through a
  pull request that Leo merges.
- Commits use your own git identity.
