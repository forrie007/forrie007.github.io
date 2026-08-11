# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

> Authoritative source of truth for this repository's purpose and structure.

---

## Architecture Overview

This repository is the **GitHub Pages user site** for `forrie007`. It hosts a minimal landing page at
`https://forrie007.github.io` and serves as the DNS root under which all other GitHub Pages sites in
this account are accessible (e.g. `https://forrie007.github.io/helm-charts`).

**There are no build steps, no CI workflows, and no Renovate-managed dependencies.**
Content is served directly from the `main` branch by GitHub Pages.

### Files

| File | Purpose |
|------|---------|
| `index.html` | Landing page — served at `https://forrie007.github.io` |
| `README.md` | Repository description |

### Relationship to other repos

The Helm chart registry at `https://forrie007.github.io/helm-charts` is served from the
`forrie007/helm-charts` repository (a separate GitHub Pages site), not this one.

**That Pages-based chart registry is legacy.** The home lab cluster's `forrie` HelmRepository in
`flux-repository` was migrated to OCI (`oci://ghcr.io/forrie007/charts`), and the chart repos publish
there via the `publish-helm-to-ghcr-oci.yaml` reusable workflow. The Pages path
(`publish-helm-to-helm-charts.yaml`) still exists in `forrie007/.github` but is not what Flux consumes.

---

## Renovate PR Review Checklist

**No Renovate-managed dependencies exist in this repository.**
If Renovate opens a PR against this repo, it is unexpected — verify it is not misconfigured.
