# 04 – Remote workflow: GitHub, origin, push/pull, clone

**Mål:** Koppla lokalt repo till GitHub, pusha och hämta.

## Steg
1) Skapa **tomt repo på GitHub** (via webben), kopiera URL → lägg som `origin`:
```bash
git remote add origin https://github.com/<user>/hello-git.git
git branch -M main
git push -u origin main
```

2) Gör en ny commit lokalt → push

3) Simulera “ny maskin”: klona i ny mapp (valfritt):
```bash
cd ..
git clone https://github.com/<user>/hello-git.git hello-git-2
cd hello-git-2
git pull
```

## Checklista
- [ ] origin satt och main pushad
- [ ] Kloning fungerar och pull hämtar senaste 
