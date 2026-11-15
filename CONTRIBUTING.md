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
./dev-server.sh [--no-dev-mode] [--lan] [port]   # or dev-server.bat on Windows; --lan for phones on the home network
```

## Branches and going live

- **`main` is what's live.** Nothing is pushed to it directly: it only changes when a pull request from `staging` is merged, with a merge commit so the release tags stay in its history. GitHub Pages publishes the status page from it.
- **`staging` is the last check before live.** It only changes when a pull request from `test` is merged. Nothing deploys from it: there's no staging copy of this page.
- **Work happens on `test`**, or on a branch off it that's merged back into it. Releases are made there too: `commit.sh` / `commit.bat` refuse to run on `staging` or `main`.
- **Going live:** push `test` with its tag (`git push origin test --tags`), open a pull request into staging (`gh pr create --base staging --head test`), check staging once it's merged, then open one from staging into main (`gh pr create --base main --head staging`). Leo merges both.
- Before opening a pull request, merge the branch it goes into back into yours if it has moved.
- **The one exception:** the Status workflow (GitHup) commits the monitors' data to `main` on its own every few minutes. Merge `main` into `test` before starting new work.

## Project conventions

- **What's monitored** lives in `.githup.yml` only. Public family websites only: never the homelab's services.
- **Don't edit `data/`** by hand: GitHup writes it.
- **Releases:** [Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, plus `-1`, `-2`... for
  later releases the same day). v26.11.06 was the first stable release, and there's no going back to `0.x.y`. Update `CHANGELOG.md` (sections in the order Added, Changed, Fixed, Removed,
  Security, Deprecated), bump `VERSION.md`, run `bash tests/version.sh`, then `./commit.sh` (or `commit.bat`). Work goes on `test`, and reaches `main` through
  `staging` (Branches and going live).
- Commits use your own git identity.
