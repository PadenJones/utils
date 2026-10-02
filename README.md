# utils

A centralized repository for reusable code shared across projects, and a controlled environment for validating npm package publishing and release workflows.

## Purpose

- **Shared code** – Common utilities and modules maintained in a single location so they can be consumed consistently by multiple projects.
- **Release testing** – A safe sandbox for exercising npm package release processes, including versioning, tagging, and publishing (stable and pre-release).

## Getting Started

```sh
npm install
```

The package is published as `@padenjones/utils`. Publishing requires being logged in to npm (`npm login`).

## Scripts

Run any script with `npm run <script>`.

### Development

| Script   | Description                          |
| -------- | ------------------------------------ |
| `format` | Format the codebase with Prettier.   |

### Inspecting

| Script     | Description                                                   |
| ---------- | ------------------------------------------------------------- |
| `pack:dry` | Preview the package contents that would be published.         |
| `view`     | Show the published package metadata from the npm registry.    |

### Stable Releases

Each command bumps the version (creating a git commit and tag) and then publishes to the `latest` dist-tag.

| Script          | Description                                           |
| --------------- | ----------------------------------------------------- |
| `release:patch` | Bump the patch version (e.g. 1.0.9 → 1.0.10) and publish. |
| `release:minor` | Bump the minor version (e.g. 1.0.9 → 1.1.0) and publish.  |
| `release:major` | Bump the major version (e.g. 1.0.9 → 2.0.0) and publish.  |
| `release`       | Publish the current version without bumping it.       |

### Beta Releases

Beta versions are published under the `beta` dist-tag, so they are not installed by default.

| Script         | Description                                                              |
| -------------- | ------------------------------------------------------------------------ |
| `beta:start`   | Start a new beta line (e.g. 1.0.9 → 1.0.10-beta.0) and publish.          |
| `beta:next`    | Increment the beta prerelease (e.g. 1.0.10-beta.0 → 1.0.10-beta.1) and publish. |
| `release:beta` | Publish the current version under the `beta` tag without bumping it.     |

Install a beta with `npm install @padenjones/utils@beta`.

### Maintenance

| Script          | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| `unpublish:all` | Force-unpublish every version of the package. **Destructive; use with care.** |
