# Git Workflow

Git is learned **by doing**, in the flow of the project — not as a class. Reference: [Learn Git Branching](https://learngitbranching.js.org/) · [Oh My Git](https://ohmygit.org/) · [Pro Git](https://git-scm.com/book).

## Branch model

| Branch | Purpose | Who |
|---|---|---|
| `main` | Plans, standards, tracker, README | Coach-owned; learners don't commit |
| `helena/foundations` | Helena's Phase 1 learning | Helena |
| `thomas/foundations` | Thomas's Phase 1 learning | Thomas |
| `dev` | Integration branch for build phases | Both (via PR) |
| `feat/*` | Feature work in Phase 2+ | Whoever owns the task |

`Plan` is retired.

## Daily loop

```
git switch <your-branch>
git pull --rebase
# ... work ...
git add -p
git commit -m "feat: ..."
git push
```

- Commit **daily**, even 10 lines.
- [Conventional Commits](https://www.conventionalcommits.org/): `feat: fix: chore: docs: test: refactor:`.
- Open a **PR** for build-phase work; Thomas reviews Helena's, comments, requests changes — she pushes again. He does not push fixes into her branch.

## Skills to hit by doing

`status`, `add -p`, `commit`, `push`, `pull --rebase`, `log --oneline --graph`, `switch -c`, `merge`, `diff`, `restore`, `reset --soft/--hard`, `revert`, `stash`, `blame`, `show`.

**Deliberately create a merge conflict and resolve it — twice.** Everyone fears this until they've done it.
