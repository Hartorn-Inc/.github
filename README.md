# Hartorn-Inc `.github`

Organization-wide community health defaults and shared Renovate presets for `Hartorn-Inc` repositories.

This repository is public because GitHub only applies default community health files from a public `.github` repository. Never commit secrets or private data here.

## Community Health Files

- `CONTRIBUTING.md`: clarifies that external pull requests are not accepted.
- `SECURITY.md`: directs vulnerability reports to GitHub Private Vulnerability Reporting.

## Renovate Presets

| Preset | Purpose |
| --- | --- |
| `github>Hartorn-Inc/.github` (`default.json`) | Extends `github>Giskard-AI/.github` (7-day `minimumReleaseAge`, 0-day `vulnerabilityAlerts`, Monday schedule), sets `npmrc: "ignore-scripts=true"`, and disables un-cooled `lockFileMaintenance` by default. |
| `github>Hartorn-Inc/.github:automerge` (`automerge.json`) | Extends `github>Giskard-AI/.github:automerge` and enables native automerge (behind required CI + zizmor Gate checks) for non-major `npm`/`pep621`/`cargo` updates, non-major `github-actions` `uses:` updates + `pinDigest`, and Docker Hub `dockerfile`/`docker-compose` `minor`/`patch`/`digest` updates (excluding `ubuntu` releases, `major` updates, `digest`-only action tag moves, and `vulnerabilityAlerts`). |

### Usage

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>Hartorn-Inc/.github",
    "github>Hartorn-Inc/.github:automerge"
  ]
}
```
