### Vett & Etikett: När göra commit
* Commita när en logisk bit/komponent ÄR KLAR i koden.
* ELLER du har löst ett problem (bug/issue)
* Commita ofta
* Tänk Att Dela upp en funktions implementering i logiska bitar som kan slutföras någorlunda snabbt så att du kan commita ofta.
* Testa koden innan commit.
* Commita ALDRIG halvfärdig kod.
* Allt detta är Superviktigt om vi senare gör en reset/revert till en tidigare commit.

### Vett & Etikett: Commit meddelande VIKTIGT
Välformulerade commit-meddelande är nödvändigt när du jobbar i projekt med flera deltagare.
* Använd engelska
* Beskriv VILKEN funktionalitet som lagts till eller problem som din commit löst.
* Beskriv VARFÖR denna funktionalitet behövs, inte hur du löst den.

```bash
git commit -m "Add margin to nav items to prevent them from overlapping the logo"
			  VILKEN /               VARFÖR /
```


## Vett & Etikett: Längre commit meddelande

### Strukturerat commit meddelande
En strukturerad commit meddelande ska innehålla:
* Typ: feature, fix (buggfix), doc m.m.
* Rubrik: Vilken & Varför
* Meddelande: (valfri) Beskrivning av.
* Fotnot: (valfri) Referens ex issue-nr.


TYP : Rubrik
MEDDELANDE
..........
Fotnot


### Git Bash
Git Bash är ett konsol program (shell).
pwd: lista vilken mapp jag står i.
ls: lista mappens innehållet
ls -l: lista mappens innehåll med info
ls -a: lista även hemliga mappar/filer
mkdir: skapa mapp ex **mkdir mitt_proj**
cd: byt mapp ex **cd mitt_proj**
touch: skapa tom fil, ex **touch fil.txt**
cat: skriv ut en fils innehåll, ex **cat fil.txt**

## Editors

### BASH: editorer & öppna VS code från Bash

- Finns flera editorer: vim, emacs, nano (lättast)

Öppna readme.md med nano

### Nano enklast
^ = CTRL
^O = Write out (Spara till fil)
^R = Read file
^X = Exit

### Git standard editor (VIM) kommer upp ibland

* 2 lägen, byta läge med Esc
	* Kommando läge
		* Vi kan skriva kommandon längst ner
			* :i insert, vi kan lägga in text
			* :wq, skriv till fil och avsluta
	* Editerings-läge
		* Vi kan skriva i filen.

## GIT
Versionshanteringssytem - Sparar versioner av ett projekt/fil. Håller reda på sparade förändringar, av vem, när & varför. Om det blir fel kan vi gå tillbaka till en tidigare version av filen. Nedan visas ett repo med 3 sparade versioner av 1 fil.

Branch = Projekts olika utvecklingsgrenar (sägs om vi har ett företag vi gör en tjänst som 10000 kunder använder och betalar för jätte viktigt funkar ny funktionalitet så måste det här funka det måste funka så kan man ha flera olika brancher så man kan ha t.ex en för att release till public och en annan för att arbeta med nya features. En för att testa och utveckla och en till production som används av kunder.)


REPO - Ett projekt unnehållande branch(er), filer och sparade ändringar
BRANCH (gren) - Är en utvecklingsgren av ett projekt. Ett repo kan innehålla flera grenar ( En produktion och flera feature-branches ex)
HEAD: pekar vart vi jobbar (ex i v.2 i Master)


### Filer som GIT ska ignorera - .gitignore
* Ofta ha rvi filer som i ett projekt som inte ska ingå i repot.
* Exempelvis:
	* Build filer (mappar)
	* kompilerad kod som exe-filer, .class-filer (java)
* Vi lägger allt som GIT ska ignorera i filen .gitignore
	* Ignorera mapp: /mapp_namn
	* Ignorera fil: start.exe
* Använda mönster för filer mappar
	- *.exe ignorerar alla filer som slutar på .exe.

### Exempel .gitignore
* Filer (ej.txt) och mappar (ej) som är angivna i .gitignore filen kommer ignoreras av git

.gitignore : ej.txt /ej -> mappen ej och filen ej.txt


### GIT repository
En repo (repository) är en container för ett project som du vill att GIT spårar ändringar i. Du skapar en repo för en mapp med __git init__.

- git init skapar mappen .git innehållande alla uppgifter om din repo, ta bort mappen så tas repon bort.


### GIT filers olika tillstånd

När en ändring(version) sparats i GIT så är filen committed.
En fil kan ha 4 tillstånd
* Untracked - Git struntar i filen.
* Modified - Filen har ändrats.
* Staging - Förberedd för commit.
* Committed - Version har sparats.

För att  spara gjorda ändringar i GIT så:
* Förbered fil för commit med "git add ."
* Commita med git commit -m "meddellande"
* Dom filer vi vill att GIT ignorerar lägger vi in filen .gitignore


git add . = lägger till alla filer

### Git commit --ammend: Om meddelandet blir fel

* Om vi vill skriva om commit meddelandet så använder vi: git commit --amend

### GIT status & fil tillstånd
git status visar status på repon & filerna:
* modified (Fil är ändrad)

	* Vi kör git add.
* Staging status: Visar vilka filer som har blivit modifierad


### Git restore: Gå tillbaka från staged/modified

För ändra status på en fil från staging till Modified
git restore --staged fil.txt

För ändra status på en fil från Modified till Unmodified
git restore fil.txt

### Git log
När vi har gjort flera commits kan vi se dessa med __git log__.
Om vi vill se en komprimerad version av logen __git log -oneline__

### Git diff - se skillnaden i fil på versioner

* Git diff visar skillnad i fil-innehållet mellan versioner
* Vi vill jämföra den 3:e (ae2ae14) med senaste (head): git diff ae2ae14 head

ae2ae14: a/fill.txt
head: b/fill.txt

--- = a filen (ae2ae14) 
+++ = b filen (head) senaste versionen



### Ta bort Branch

git branch -D (branchname)



### Merge: Skicka ändringar från branch till Master
När vi är klar med arbetet på ny_branch
så måste skicka ändringarna till Master & till sist ta bort ny branch 
flytta head till master



### Merge conflicts
Ibland så kan en fil ändras i både master och en under-branch innan en merge ska göras, då är risken stor att det uppstår en merge conflict.
Detta innebär att mergen avbryts och vi måste gå in och ändra den filen som är osaken till denna.

Undviks genom att göra pull ofta till ny branch

Gör git pull ofta så man vet att man har fresh code


### Merge conflicts
Ibland vi ska merga 2 brancher så uppstår en konflikt
Merge-operationen avbröts.

Öppna filen som är involverad i konflikten.

Filen har fått information om konfilkten. <<<<<Head start konflikt, === gräns kod branchar och >>> branch:namn slut-konflikt.

Editera filen som den ska se ut. Spara & Avsluta filen

Kör git add
git commit __utan meddelande__

Kolla logen och se att merge genomförd


### Flera brancher jobbar mot master/main
* När flera jobbar mot master/main repot så behöver vi uppdatera den nya branchen OFTA så vi minimerar **risken för merge conflict**
* Vi uppdaterar den nya branchen med **Pull**




## Viktigt
Kör alltid en pull innan man kör en push för att minska risken för merge conflicts




### Remote origin URL
När vi klona ett github repo så skapas en alias som heter origin












