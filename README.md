# canopy-cli

Nix packaging for `@os-eco/canopy-cli` using Bun and `bun2nix`.

## Package

- Upstream package: `@os-eco/canopy-cli`
- Pinned version: `0.2.3`
- Description: Git-native prompt management for AI agent workflows
- Installed binary: `canopy`
- Upstream executable invoked by Bun: `cn`

## What This Repo Does

- Uses `bun.lock` and generated `bun.nix` as the dependency lock surface for Nix
- Builds the upstream package as an internal Bun application with `bun2nix`
- Exposes only the canonical binary name `canopy`
- Provides a manifest sync script for updating the pinned npm metadata

## Files

- `flake.nix`: flake entrypoint
- `nix/package.nix`: Nix derivation
- `nix/package-manifest.json`: pinned package metadata and exposed binary name
- `scripts/sync-from-npm.ts`: updates pinned npm metadata without changing the canonical output binary

## Notes

- The default `out` output installs the longform binary name `canopy`.
- The shortform name `cn` is available as a separate Nix output, not in the default `out` output.
