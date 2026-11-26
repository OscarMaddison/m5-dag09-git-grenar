# Git-logg

Klistra in utskrifter och svara på frågorna. Det här är din dokumentation av dagens arbete.

## 1. Utgångsläget
Skriv ut `git log --oneline --graph --all` direkt efter att du klonat. Klistra in här:

```
* 5a5841d (HEAD -> main, origin/main, origin/HEAD) Modul 5 i TypeScript med Vite
* 3804533 Add files via upload
* f7a13a4 Add files via upload
* c9a0075 Initial commit
```

## 2. Merge utan konflikt
Klistra in `git log --oneline --graph --all` efter merge:

```
*   cf54f72 (HEAD -> main) Merge branch 'meny-nyheter'
|\  
| * 8713acc (meny-nyheter) Lägg till kanelbulle på menyn
* | 17208f2 Lägg till telefonnummer
|/  
* 3d3e9aa Dag 9: Steg 1
* 5a5841d (upstream/main, upstream/HEAD, origin/main, origin/HEAD) Modul 5 i TypeScript med Vite
* 3804533 Add files via upload
* f7a13a4 Add files via upload
* c9a0075 Initial commit
```

Fråga: Vad är skillnaden mellan en *fast-forward*-merge och en merge som skapar en egen merge-commit? Svara med egna ord:
En fast-forward uppdaterar en gren till en annan, en merge harmoniserar ändringarna i två olika grenar.

## 3. Konflikten
Klistra in filen med konfliktmarkörerna, precis som den såg ut innan du löste den:

```
# Öppettider

Vardagar: 07–18
<<<<<<< HEAD
Helger: 10–17
=======
Helger: 09–18
>>>>>>> oppettider-sommar
Röda dagar: stängt

```

Fråga: Vad betyder `<<<<<<< HEAD`, `=======` och `>>>>>>> grennamn`?
Vid en merge-konflikt så signalerar och avgränsar det raderna som är i konflikt, och visar vilken som hör till vilken version.

Hur löste du den, och varför blev det så?
Jag ersatte bägge med en ny tid, för jag brydde mig inte om att välja mellan dem.

## 4. Ångra
Vad är skillnaden mellan `git restore`, `git revert` och `git reset`? Vilken är säkrast när ändringen redan är pushad?
Git restore tar bort ocommittade ändringar, git revert tar bort ändringar men behåller historiken, och git reset tar tillbaka grenen till en tidigare tidpunkt och raderar alla ändringar efter den tidpunkten. Git revert är därmed säkrast för att ångra pushade ändringar.

## 5. Pull request
Länk till din pull request (på ditt eget repo):
https://github.com/Lexicon-RC/m5-dag09-git-grenar/commit/f73f4827794a5781ca910d30c93e2d05145eb007
error: branch 'info-uppdatering' not found

## 6. Reflektion
Vad är det värsta som kan hända om man kör `git push --force` på en gren som andra använder?
Allt arbete som end medarbetare gjort sedan ens senaste merge kan raderas.

