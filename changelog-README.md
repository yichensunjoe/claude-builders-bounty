# Changelog Generator

A Bash script that auto-generates a structured `CHANGELOG.md` from your git history, following [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) conventions.

## Quick Start (3 steps)

```bash
# 1. Make executable
chmod +x changelog.sh

# 2. Run in any git repo
./changelog.sh

# 3. View the result
cat CHANGELOG.md
```

## Usage

```bash
# Default: from last tag → HEAD
./changelog.sh

# Custom range
./changelog.sh --since v1.0.0 --to v2.0.0

# Write to custom file
./changelog.sh --output HISTORY.md

# Help
./changelog.sh -h
```

## How It Works

1. **Fetches** all commits since the last git tag
2. **Auto-categorizes** each commit by its message prefix:

   | Prefix | Category |
   |--------|----------|
   | `add:` `feat:` `new:` `implement:` `create:` | Added |
   | `fix:` `bug:` `patch:` `resolve:` `hotfix:` | Fixed |
   | `change:` `update:` `modify:` `refactor:` `improve:` | Changed |
   | `remove:` `delete:` `drop:` `deprecate:` `cleanup:` | Removed |

3. **Outputs** a formatted `CHANGELOG.md` with version, date, and categorized entries including hash, author, and date.

## Sample Output

See [CHANGELOG.md](CHANGELOG.md) for an example generated from this repo's own git history.
