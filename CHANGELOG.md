# Changelog

All notable changes to the Ridgwell Family's status page (status.ridgwell.family) are documented here. Sections follow
a fixed order: Added, Changed, Fixed, Removed, Security, Deprecated. This project is pre-stable, on
[Semantic Versioning](https://semver.org) `0.x.y`; its first stable release will be its first
[Date Version](https://datevers.ing) (`YY.MM.DD`), with no 1.0.0.

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
