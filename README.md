# repos-daily-monitor

Daily GitHub Actions workflow that reviews the repositories of the GitHub profile [Mar2rech](https://github.com/Mar2rech) and records changes (new or removed repositories) in the `CHANGES.md` file.

## How it works

- Runs automatically every day at 07:00 UTC (08:00 CET).
- Can also be triggered manually from the Actions tab.
- Fetches the current list of public repositories.
- Compares it against the previous snapshot (`previous_repos.txt`).
- Appends detected changes to `CHANGES.md`.
- Commits and pushes the updates if there are changes.

## Files

- `.github/workflows/daily-repos-monitor.yml`: The workflow definition.
- `CHANGES.md`: Log of repository list changes over time.
- `previous_repos.txt`: Snapshot of the last known list of repositories (created on first run).

## Notes

- The first run creates a baseline snapshot in `CHANGES.md`.
- Only tracks additions and removals of repositories in the list (not internal changes like stars or commits). You can extend the workflow for more details if needed.
- Uses the built-in `GITHUB_TOKEN` for API access.

Repository created and configured via Grok.
