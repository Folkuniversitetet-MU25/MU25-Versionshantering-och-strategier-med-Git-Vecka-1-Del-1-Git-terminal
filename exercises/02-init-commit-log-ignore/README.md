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
Commit 1 – rubrik
```bash
git add README.md
git commit -m "docs: add title"
```
Commit 2 – nytt avsnitt
Öppna README.md i valfri editor (t.ex. VS Code/Notepad/TextEdit), lägg till en rad (t.ex. Intro text) och spara.
```bash
git add README.md
git commit -m "docs: add intro section"
```

Commit 3 – liten rättning
Öppna README.md igen, ändra en formulering (t.ex. “Intro” → “Introduction”) och spara.
```bash
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
