# 05 – Ångra säkert: restore, amend, (försiktigt) reset

**Mål:** Träna på att ångra utan panik – börja säkert.

## Steg
1) **Ångra staged men ej committat**
```bash
echo "temp line" >> README.md
git add README.md
git restore --staged README.md   # tar bort från staging
git restore README.md            # ångrar arbetskopia
```

2) **Rätta senaste commit (amend)**
```bash
echo "extra note" >> README.md
git add README.md
git commit --amend -m "docs: add extra note to README"
```

3) **Reset (försiktigt): visa skillnaden**
```bash
git log --oneline

# Skapa 2 snabba commits
echo "a" >> A.txt && git add A.txt && git commit -m "chore: add A"
echo "b" >> B.txt && git add B.txt && git commit -m "chore: add B"

# Soft: behåll ändringar som staged
git reset --soft HEAD~1

# Mixed (default): behåll ändringar i working tree, men unstaged
git reset HEAD~1

# Hard: KASTA ändringar (gör detta bara på eget ansvar, aldrig på pushad historik)
# git reset --hard HEAD~1
```

## Checklista
- [ ] Du kan förklara när restore, amend och reset är lämpliga
- [ ] Du vet att reset --hard aldrig ska användas på pushad historik
