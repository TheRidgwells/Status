<p align="center">
  <img src="https://projects.ridgwell.family/assets/img/projects/ridgwell-status-icon.png" height="100" alt="Ridgwell Status icon">
</p>

# Ridgwell Status

### *Live status of the Ridgwell Family's websites, powered by [GitHup](https://github.com/StuxGroup/GitHup).*

**Status page:** [status.ridgwell.family](https://status.ridgwell.family)

## Current status

Updated by GitHup whenever the status page is rebuilt (hourly, and when a status changes).

<!-- githup:start -->
<!-- This table is written by GitHup (https://github.com/StuxGroup/GitHup); edits here are overwritten. -->

**All systems operational** · [Live status page](https://status.ridgwell.family/)

| Group | Monitor | Status | Uptime (24 h) | Uptime (7 d) | Uptime (30 d) | Response time (24 h) |
| ----- | ------- | ------ | ------------- | ------------ | ------------- | -------------------- |
| The Ridgwell Family | [The Ridgwell Family](https://the.ridgwell.family/) | Up | 100.00% | 100.00% | 100.00% | 1156 ms |
| The Ridgwell Family | [Leo JD Ridgwell](https://leo.ridgwell.family/) | Up | 100.00% | 100.00% | 100.00% | 1218 ms |
| The Ridgwell Family | [Elisia](https://elisia.ridgwell.family/) | Up | 100.00% | 98.98% | 98.98% | 1176 ms |
| The Ridgwell Family | [The Ridgwell Cats](https://cats.ridgwell.family/) | Up | 100.00% | 100.00% | 100.00% | 844 ms |
| The Ridgwell Family | [The Ridgwell Archives](https://archives.ridgwell.network/) | Up | 100.00% | 99.48% | 99.48% | 691 ms |
| Shared | [Ridgwell Family Media](https://global.media.ridgwell.family/icon.png) | Up | 100.00% | 100.00% | 100.00% | 422 ms |
<!-- githup:end -->

## What's monitored

Every 5 minutes (when GitHub runs the schedule late, a run checks up to 4 times, 5 minutes apart, to fill the gap),
GitHup checks each monitor in [`.githup.yml`](.githup.yml):

- **The Ridgwell Family:** [the.ridgwell.family](https://the.ridgwell.family), [leo.ridgwell.family](https://leo.ridgwell.family),
  [elisia.ridgwell.family](https://elisia.ridgwell.family), [cats.ridgwell.family](https://cats.ridgwell.family) and
  [archives.ridgwell.network](https://archives.ridgwell.network)
- **Shared:** the family's media server, global.media.ridgwell.family

Only the family's public websites are here. The homelab's own services are private, and Ridgdash watches those.

To add a site, add a monitor to the right group in `.githup.yml` (or a new group).

## How it works

`.github/workflows/status.yml` runs [GitHup](https://github.com/StuxGroup/GitHup): it checks the monitors, commits
their history to `data/`, opens and closes an Issue labelled `status` for each outage, rebuilds the page (with its
legal pages, sitemap and 404 page) and deploys it to GitHub Pages. The custom domain is set in the repo's Pages
settings.

## Local development

```bash
./dev-server.sh [--no-dev-mode] [port]   # or dev-server.bat on Windows; Python 3.11+
```

It builds the page from `.githup.yml` with 90 days of example data and serves it on http://127.0.0.1:8000, with
GitHup's DEV MODE banner (leave it off with `--no-dev-mode`).

## Versioning

[Date Versioning](https://datevers.ing): each release is the UTC release date as `YY.MM.DD`, plus `-1`, `-2`... for
later releases the same day. v26.11.06 was the first stable release (there was no 1.0.0; before it, the project was
pre-stable on `0.x.y`), and it never goes back to `0.x.y`. To release: update
`CHANGELOG.md`, bump `VERSION.md`, run `bash tests/version.sh`, then `./commit.sh` (or `commit.bat`), and push `main`
and the new tag.

## Licence

Copyright © 2026 The Ridgwell Family. All rights reserved; see [LICENSE](LICENSE).

---

*Built & Maintained by <img src="https://leo.media.ridgwell.family/icon.png" height="14" alt="Leo JD Ridgwell" valign="middle"> [Leo JD Ridgwell](https://leo.ridgwell.family), Hosted by <img src="https://github.com/TheRidgwells.png" height="14" alt="The Ridgwell Family" valign="middle"> [The Ridgwell Family](https://the.ridgwell.family).*
