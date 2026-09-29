# aeon-poc

Replica of aeon-toolkit/aeon's PR pre-commit workflow.

Demonstrates fork checkout + pre-commit hook code execution:
- `pull_request_target` triggers on any fork PR (no gate, no type filter)
- Both jobs check out the fork's code as the working directory
- `pre-commit/action` executes `.pre-commit-config.yaml` from the workspace
- Attacker replaces `.pre-commit-config.yaml` with a `local` hook containing exfil commands
- The checkout token (GitHub App / PAT) is extractable from the git credential store

Used for authorized security research only.
