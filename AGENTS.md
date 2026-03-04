# Agent Instructions

This project uses **ggbd** (beads) for issue tracking. Run `ggbd prime` to load workflow context.

## Quick Reference

```bash
ggbd ready              # Find available work
ggbd show <id>          # View issue details
ggbd update <id> --status=in_progress  # Claim work
ggbd close <id>         # Complete work
# Supabase auto-syncs (no manual sync needed)
```

## Session Completion Protocol

**When ending a work session**, use the conductor completion pipeline:

```bash
/conductor:verify-build      # Build and check for errors
/conductor:code-review       # Opus review with auto-fix
/conductor:commit-changes    # Stage + commit
/conductor:close-issue <id>  # Close beads issue
# Supabase auto-syncs (no manual sync needed)
```

Or use the full pipeline: `/conductor:worker-done <id>`

**CRITICAL RULES:**
- Work is NOT complete until `git push` succeeds
- NEVER stop before pushing - that leaves work stranded locally
- NEVER say "ready to push when you are" - YOU must push
- If push fails, resolve and retry until it succeeds

## For More Details

See `.beads/PRIME.md` for complete workflow documentation including:
- All `ggbd` commands
- Dependency management
- Multiple completion pipeline options
- Common workflow patterns
