# Vecka 1 – Del 1: Git & terminal (solo-flöde)

(Test text bara för att ha något att skicka upp till remote repot.)

Fokus: grunder i Git via **terminal** (Git Bash("Linux-miljö")/macOS). Repon, staging, commits, branches, merges, `.gitignore`, `README`, autentisering (SSH/PAT) samt push/pull.

> **Viktigt om upplägg**  
> • Övningarna **lämnas inte in i Azomo**.  
> • Varje student jobbar i **eget repo** (du skapar och kör allt lokalt/egen GitHub).  
> • **Gör inget mot lärarens repo.**  
> • PR är **frivilligt** denna vecka (du jobbar solo). Vill du öva PR? Öppna PR i **ditt eget repo**.

## Snabblänkar till övningar

- [01 – Setup & Auth (git config, PAT/SSH)](exercises/01-setup-auth/README.md)
- [02 – Första repo: init → add → commit → log → .gitignore](exercises/02-init-commit-log-ignore/README.md)
- [03 – Branch & Merge (fast-forward och no-ff)](exercises/03-branch-merge-basics/README.md)
- [04 – Remote workflow: GitHub, origin, push/pull, clone](exercises/04-remote-push-pull/README.md)
- [05 – Ångra säkert: restore, amend, (försiktigt) reset](exercises/05-undo-basics/README.md)
- [Bonus – Markdown för README](exercises/06-markdown-bonus/README.md)

## Så arbetar du (ingen inlämning)

1. Skapa **eget repo** för vecka 1 (t.ex. `mu25-v1-ditt-namn`) och jobba där.
2. Kör igenom övningarna i ordning.
3. (Frivilligt) Öppna PR i ditt repo för att träna.
4. Be gärna en klasskompis kika på din historik/README och ge feedback.

## Förutsättningar

- Git installerat och konfigurerat (`user.name`, `user.email`, `init.defaultBranch=main`)
- Autentisering mot GitHub (PAT eller SSH)
- Editor/IDE (VS Code rekommenderas)

## Konventioner för commit-meddelanden (enkelt)

- Skriv kort och i imperativ: “add”, “fix”, “update”.
- Exempel: `feat: add welcome section to README`
- Håll en commit till **en logisk ändring**.

## Troubleshooting (vanligt)

- `fatal: not a git repository` → Kör kommandot i rätt mapp (där `.git/` finns) eller kör `git init`.
- `Permission denied (publickey)` → SSH-nyckel saknas/fel; följ GitHubs SSH-guide. Alternativt kör HTTPS + PAT.
- `Support for password authentication was removed` → Använd **PAT (HTTPS)** eller **SSH-nyckel** (lösenord funkar inte längre).
- Konstiga radbrytningar (Windows/macOS) → Sätt `core.autocrlf`:
  - Windows: `git config --global core.autocrlf true`
  - macOS/Linux: `git config --global core.autocrlf input`

### Bonus: global ignore & credential helper

- Global ignore (OS/IDE-filer):

```bash
  echo ".DS_Store" >> ~/.gitignore_global
  git config --global core.excludesFile ~/.gitignore_global
```

- Credential helper (hantera PAT/credentials):
  Windows: git config --global credential.helper manager
  macOS: git config --global credential.helper osxkeychain
  Linux (enkelt): git config --global credential.helper store
