# 03 – Branch & Merge (fast-forward och no-ff)

**Mål:** Förstå enkel branching och skillnaden fast-forward vs no-ff.

## Steg
1) Skapa feature-branch och gör ändringar
```bash
git checkout -b feat/welcome
echo "Welcome section" >> README.md
git add README.md
git commit -m "docs: add welcome section"
```

2) Testa fast-forward merge
```bash
git checkout main
git merge feat/welcome   # blir fast-forward
git log --oneline --graph --decorate
```

3) Testa no-ff (merge-commit även om FF möjligt)
```bash
git checkout -b feat/tips
echo "Tips section" >> README.md
git add README.md
git commit -m "docs: add tips section"
git checkout main
git merge --no-ff feat/tips -m "merge: add tips feature"
git log --oneline --graph --decorate
```

## Checklista
- [ ] Du har gjort både en FF-merge och en no-ff-merge
- [ ] Du kan förklara skillnaden (historikens utseende & spårbarhet)
