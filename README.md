# Git-Based Semantic Versioning Action

A GitHub Action that manages semantic versioning using git tags - no configuration files needed! This action won't modify any files in your repository.

## Quick Start

Add this to your GitHub workflow:

```yaml
- name: Update Version
  uses: tuanngocptn/semantic-versioning-action@main
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  with:
    script: increment_core_tag patch  # Choose patch, minor, or major
```

## Version Types

### Core Versions
- `increment_core_tag patch` → Bumps 1.0.x (e.g. 1.0.1 -> 1.0.2)
- `increment_core_tag minor` → Bumps 1.x.0 (e.g. 1.0.1 -> 1.1.0)
- `increment_core_tag major` → Bumps x.0.0 (e.g. 1.0.1 -> 2.0.0)

### Environment Versions
- `increment_tag dev`   → Development build
- `increment_tag stg`   → Staging build
- `increment_tag uat`   → UAT build
- `increment_tag alpha` → Alpha release
- `increment_tag beta`  → Beta release

## Local Usage

Want to run this locally? Create a `version.sh` file:

```bash
source /dev/stdin <<<"$(curl -s https://raw.githubusercontent.com/tuanngocptn/semantic-versioning-action/main/index.sh)" && get_stage_prompt
```

Then run:
```bash
bash version.sh
```

You'll see an interactive menu:
```
Action:
1) Development build  5) Patch version (1.0.x)
2) Staging build      6) Minor version (1.x.0)
3) UAT build          7) Major version (x.0.0)
4) Production build   8) Quit
```

## Contributing

Please see [CONTRIBUTING.md](CONTRIBUTING.md) for development guidelines.

---
Built with ❤️ for easier version management
