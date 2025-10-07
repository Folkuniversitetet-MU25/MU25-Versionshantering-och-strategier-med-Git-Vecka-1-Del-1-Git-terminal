# 01 – Setup & Auth (git config, PAT/SSH)

**Mål:** Få en fungerande terminal-miljö med rätt identitet och autentisering.

## Steg
1) **Git config**
```bash
git config --global user.name "Förnamn Efternamn"
git config --global user.email "din@mail"
git config --global init.defaultBranch main
git config --global color.ui auto
```

2) **Autentisering**
Välj en metod:
PAT (HTTPS): Skapa Personal Access Token i GitHub → logga in vid första push.
SSH: Generera nyckel (ssh-keygen -t ed25519), lägg public key i GitHub → testa ssh -T git@github.com.

2) **Verifiera**
```bash
git --version
git config --list
```

Checklista (självkontroll)
- [ ]  git config visar korrekt namn/e-post
- [ ]  PAT eller SSH fungerar mot GitHub (testad)
