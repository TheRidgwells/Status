# Changelog

All notable changes to the Ridgwell Family's status page (status.ridgwell.family) are documented here. Sections follow
a fixed order: Added, Changed, Fixed, Removed, Security, Deprecated. This project uses
[Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, plus `-1`, `-2`... for later releases that
day). v26.11.06 is its first stable release; the releases before it were pre-stable, on `0.x.y`.

## v26.11.15-2

### Changed
- **The check schedule's comment says what GitHub really does:** the workflow asks for a check every 5 minutes, but GitHub runs schedules best-effort and often less often (about one check every 45 minutes, measured on the status pages), not just "a little late".

## v26.11.15-1

### Changed
- **Branches: `test` → `staging` → `main`.** Releases are still made on `test`, and now go live through two pull requests: `test` into `staging`, then `staging` into `main`. Nothing is pushed to `staging` or `main` directly. `commit.sh` / `commit.bat` refuse to run on `staging` or `main`, and print the push (`git push origin test --tags`) and both `gh pr create` commands. CONTRIBUTING.md describes it in "Branches and going live". There's no staging copy: nothing deploys from `staging`. The Status workflow still commits the monitors' data straight to `main`, as the one exception.

## v26.11.15

### Added
- **`--lan` for the dev server** (`dev-server.sh`/`.bat`): it listens on every interface instead of only 127.0.0.1, so a phone or another device on the home network can open the local status page, and it prints the addresses to open (usually the 192.168.x.x one).

## v26.11.08

### Added

- **The cat.** The pixel cat from kat.stuxie.dev follows your pointer on every page, as Olly, with a "Your cat" picker
  in the footer, as on leo.ridgwell.family and projects.ridgwell.family (GitHup v26.11.08's `site.kat`).

### Changed

- **"Checked regularly", not "every 5 minutes".** GitHub runs the 5-minute schedule on a best-effort basis, often only
  a few times a day, so the page's description and the README no longer promise 5 minutes. The page itself now shows
  the real rhythm it's checked at (GitHup v26.11.08). The schedule is unchanged.

## v26.11.07

### Added

- **Two more monitors in The Ridgwell Family:** The Ridgwell Family Projects (projects.ridgwell.family) and Ridgwell
  Social (social.ridgwell.family). Ridgwell Social shows as down until it launches. This page doesn't monitor itself.

## v26.11.06-2

### Fixed

- `CONTRIBUTING.md` calls the page Ridgwell Status, and its release notes say the project is on Date Versioning (they
  still described the pre-stable `0.x.y` stage) and that releases reach `main` through a pull request from `test`.

## v26.11.06-1

### Changed

- The commit scripts (`commit.sh`, `commit.bat`) and `tests/version.sh` are Date Versioning only, the same as the
  other GitHup status pages' (from Stuxedo/Status): the version test's "accepts a pre-stable 0.x.y" check failed once
  the v26.11.06 tag existed, since the old scripts rightly refused 0.x.y from then on.

## v26.11.06

The first stable release, and the switch to Date Versioning for good (there is no 1.0.0). Like the other GitHup
status pages, Ridgwell Status is now treated as stable.

### Changed

- Releases use Date Versioning: the README's Versioning section and this changelog say so, and the commit scripts
  (which already accepted a Date Version) refuse to go back to `0.x.y` once v26.11.06 is tagged.

## v0.2.1

### Changed

- The page is now called **Ridgwell Status** (it was The Ridgwell Family Status), as on projects.ridgwell.family, and
  its logo and favicon are its own badge icon (the family emblem with a heartbeat badge) rather than the family's
  logo. The README's header too.

## v0.2.0

### Added

- **The Ridgwell Archives** (archives.ridgwell.network) is checked every 5 minutes too, in the family's group.

## v0.1.0

### Added

- **The Ridgwell Family's status page**, built with [GitHup](https://github.com/StuxGroup/GitHup) and deployed to
  GitHub Pages at status.ridgwell.family. Every 5 minutes it checks the family's public websites
  (the.ridgwell.family, leo.ridgwell.family, elisia.ridgwell.family, cats.ridgwell.family) and the family's media
  server. The homelab's own services aren't listed: they're private, and Ridgdash watches those.
- `commit.sh` / `commit.bat` (they read `VERSION.md`, check it, commit and tag), `tests/version.sh`, and
  `dev-server.sh` / `.bat` (a local build with example data).
