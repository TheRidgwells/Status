# Changelog

All notable changes to the Ridgwell Family's status page (status.ridgwell.family) are documented here. Sections follow
a fixed order: Added, Changed, Fixed, Removed, Security, Deprecated. This project uses
[Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, plus `-1`, `-2`... for later releases that
day). v26.11.06 is its first stable release; the releases before it were pre-stable, on `0.x.y`.

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
