# Agent Instructions

This project uses **bd** (beads) for issue tracking. Run `bd prime` to load workflow context.

## Quick Reference

```bash
bd ready              # Find available work
bd show <id>          # View issue details
bd update <id> --status=in_progress  # Claim work
bd close <id>         # Complete work
bd sync               # Sync with git
```

## Session Completion Protocol

**When ending a work session**, use the conductor completion pipeline:

```bash
/conductor:verify-build      # Build and check for errors
/conductor:code-review       # Opus review with auto-fix
/conductor:commit-changes    # Stage + commit
/conductor:close-issue <id>  # Close beads issue
bd sync && git push          # Push everything
```

Or use the full pipeline: `/conductor:worker-done <id>`

**CRITICAL RULES:**
- Work is NOT complete until `git push` succeeds
- NEVER stop before pushing - that leaves work stranded locally
- NEVER say "ready to push when you are" - YOU must push
- If push fails, resolve and retry until it succeeds

## For More Details

See `.beads/PRIME.md` for complete workflow documentation including:
- All `bd` commands
- Dependency management
- Multiple completion pipeline options
- Common workflow patterns
