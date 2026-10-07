<!-- git-workflow: v1 -->
## Git workflow
- forge: github                # github | gitlab
- status: production           # production | development | fork-submodule
- default branch: main         # main | master — protected, never push directly
- one unit of work = one short-lived branch, spun from origin/<default-branch>:
  - feat/<short-descriptive-name>   # features; OpenSpec change ⇒ feat/<change-id>
  - bug/<short-descriptive-name>    # bug fixes
- merge back: squash PR/MR into the default branch, then delete the work branch
- after a squash-merge: do NOT re-merge old branches (tips are not ancestors of the
  default branch); refresh with `git fetch --prune && git reset --hard origin/<default-branch>`
- NEVER:
  - push directly to a protected branch
  - force-push a protected branch
  - reuse an already-merged branch
  - commit directly into dev/main/master