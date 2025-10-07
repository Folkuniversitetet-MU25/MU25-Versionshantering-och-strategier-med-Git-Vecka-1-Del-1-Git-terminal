# 02 – Första repo: init → add → commit → log → .gitignore

**Mål:** Skapa ett repo, göra flera **små** commits och ignorera skräpfiler.

## Steg
1) Skapa mapp + initiera repo
```bash
mkdir hello-git && cd hello-git
git init
echo "# Hello Git" > README.md
```

2) Gör 3 logiska commits (t.ex. rubrik → avsnitt → rättning)
```bash
git add README.md
git commit -m "docs: add title"
echo "Intro text" >> README.md
git add README.md
git commit -m "docs: add intro section"
sed -i '' 's/Intro/Introduction/' README.md  # macOS (använd valfri editor)
git add README.md
git commit -m "docs: fix wording in intro"
```

3) Lägg .gitignore och visa att filer ignoreras
```bash
echo ".DS_Store" > .gitignore
mkdir build && echo "temp" > build/tmp.txt
echo "build/" >> .gitignore
git add .
git status         # build/ ska nu ignoreras
git add .gitignore
git commit -m "chore: add basic gitignore"
```

4) Utforska loggen
```bash
git log --oneline --graph --decorate
```

## Checklista
- [ ] Minst 3 commits med meningsfulla meddelanden
- [ ] .gitignore fungerar (t.ex. build/ syns inte i git status)
