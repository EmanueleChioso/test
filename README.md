# Personal GitHub Workspace

Repos in this directory use my personal GitHub account (`EmanueleChioso`), not the Zalando work account.

## How it works

**Git user/email** is automatic — `~/.gitconfig` has an `includeIf` that applies `~/.gitconfig-personal` to any repo under this directory. Commits will use the GitHub noreply email.

**SSH** is automatic — `~/.gitconfig-personal` rewrites `git@github.com:` to `git@github-personal:`, which routes through the personal SSH key (`~/.ssh/github-personal`).

**gh CLI** is NOT automatic — you must switch manually.

## Quick start

```bash
cd ~/repo/personal
just setup      # switch gh CLI to personal account
# ... do your work ...
just teardown   # switch gh CLI back to work account
```

## Commands

| Command | What it does |
|---------|-------------|
| `just status` | Show current git email and gh account |
| `just setup` | Switch gh CLI to personal account |
| `just teardown` | Switch gh CLI back to work account |
| `just clone owner/repo` | Clone a repo with personal SSH key |
| `just repos` | List all repos and their remotes |

## Cloning new repos

```bash
just clone EmanueleChioso/some-repo
just clone llmops-databricks-1/some-course
```

This uses `git@github-personal:` so the personal SSH key is used automatically.
# test
