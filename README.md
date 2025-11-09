# Matrix Build with Artifacts

## DevOps Challenge: Multi-Platform Matrix Build

This repository demonstrates a GitHub Actions workflow with matrix build strategy and artifact management.

## Features

- **Matrix Strategy**: Builds across 3 operating systems (Ubuntu, macOS, Windows) and 2 Node.js versions (18, 20)
- **Parallel Execution**: 6 jobs run in parallel (3 OS × 2 Node versions)
- **Artifact Management**: Each job generates and uploads a unique build artifact
- **Artifact Naming**: All artifacts follow the pattern `build-4cf24a1-<os>-node<version>`

## Matrix Configuration

```yaml
strategy:
  matrix:
    os: [ubuntu-latest, macos-latest, windows-latest]
    node-version: [18, 20]
```

This creates 6 parallel jobs:
- ubuntu-latest + Node 18
- ubuntu-latest + Node 20
- macos-latest + Node 18
- macos-latest + Node 20
- windows-latest + Node 18
- windows-latest + Node 20

## Artifacts

Each job generates a `build-output.txt` file containing:
- Operating system information
- Node.js version
- Build timestamp
- Runner details
- Architecture information

## Workflow Triggers

- Push to main branch
- Pull requests to main branch
- Manual workflow dispatch

## Contact

Email: 23f2003906@ds.study.iitm.ac.in
