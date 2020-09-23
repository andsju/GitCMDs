# Git guide
Gudien förutsätter att du har installerat programvaran Git (git-scm.com). I exemplet används sajten GitHub.com, och som exempel på repository: https://github.com/andsju/Example.

Versionshantering med Git hanteras i 3 olika referenser i en dator. 
* I den mapp som Git bevakar - **Working directory** - finns filer och mappar.
* **Staging area (Index)** refererar till ngt som är förberett för en förändring. Det är filer och mappar som valts ut med kommandot *git add* 
* Den tredje referensen är **Local repository** (**Head**). Den pekar på den senaste slutgiltiga förändringen. Det är filer som markerats med kommandot *git commit*

Det som nu finns i *Local repository* kan skickas till ett *Remote repository* med kommandot *git push*. Då finns en identisk kopia i molnet.

___

![Git staging](https://andsju.github.io/GitCMDs/git-illustration-1.png)

___

### Skapa ett nytt repo
I din dator:
* Skapa en ny mapp
* Öppna mappen  

Ange kommandot *git init* för att initiera möjligheten för att hantera filer och mappar.

```markdown
git init
```
Nu kan filer läggas till i ett lokalt **git repository**. En dold mapp med namnet  __.git__ bevakar innehållet i mappen. 
___

### Visa aktuell status för ett repo

Ange kommandot *git status*

```markdown
git status
```
___

### Koppla ett lokalt repo till en server 
Ta reda på adressens URL till det repo som ska kopplas - *remote repository*. Namnet *origin* är ett beskrivande namn som brukar användas för ett remote repository.
Lägg till URL:n med kommandot *git remote add*:

```markdown
git remote add origin <server>

<!-- Exempel -->
git remote add origin https://github.com/andsju/Example
```
___

### Klona ett repo
Att skapa en kopia av ett repo utförs med kommandot *git clone*:

```markdown
git clone <server>

<!-- Exempel -->
git clone https://github.com/andsju/Example
```
___


### Lägg till en fil
Skapa en ny fil i ditt lokala git repo, ex *about.txt*

När filen skapats kan du ange att filen ska inkluderas i en versionshantering med kommandot *git add*

```markdown
git add about.txt
```

För att lägga till flera filer samtidigt, kan en punkt anges efter kommandot: *git add .*

```markdown
git add .
```

När filen (filer) lagts till (redigerats) ska förändringar markeras som klara för överföring. Det görs med kommandot *git commit*. Växeln *-m* beskriver förändringen. 

```markdown
git commit -m "First commit"
```
___

### Ta bort en fil
För att ta bort en fil som lagts till i ett lokalt repo används kommandot *git rm --cached*. 

```markdown
git rm --cached file1.txt 
```

För att ta bort filen från ett lokalt repo **och filsystemet**:

```markdown
git rm file1.txt 
```
___

### Ta bort en katalog

För att ta bort en katalog från ett lokalt repo:

```markdown
git rm -r folder1 
```
___

### Skicka innehåll till server
För att skicka / pusha innehållet i ditt lokala repo till ett remote repo används kommandot *git push*

Använd växeln *-u* (--set-upstream) används om det är första gången som kommandot push används.

```markdown
git push -u origin master
```
Nästa gång räcker kommandot:

```markdown
git push origin master
```
___

### Skapa en ny branch
I Git är **master** den branch som allt utgår ifrån. Att lägga till en branch är ett sätt att göra det möjligt för en eventuell förändring av ett repo. Förändringen kan senare integreras (mergas) med **master**.

För att skapa en ny branch anges ett namn efter kommandot *git branch*. Exemeplvis en branch med namnet ex *fix1*

```markdown
git branch fix1
```
___

### Byt branch
En branch aktiveras med *git checkout*. För att aktivera *master*:

```markdown
git checkout master
```
Eller branch *fix1* (om den finns)
```markdown
git checkout fix1
```

___

### Visa branch
Visa branches med kommandot *git branch* 

```markdown
git branch
```
___

### Slå ihop (merga) en branch med en annan
Välj att aktivera den branch som ska förändras. Därefter slås en branch slås ihop med kommandot *git merge*.

```markdown
git checkout master
git merge fix1
```
___

### Ta bort en branch
En branch som finns lokalt tas bort med kommandot *git branch -d [name]*.

```markdown
git branch -d fix1
```
En branch som finns i ett remote repo tas bort med kommandot *git push [remote] --delete [branch]*.

```markdown
git push origin --delete branch fix1
```
___

### Hämta förändringar från remote server
Förändringar mellan remote och local repo visas med *git fetch*.  

```md
git fetch
```

För att hämta det innehåll som finns på en remote server till ett lokalt repo används *git pull*. Git slår ihop innehållet. Finns en konflikt visas ett meddelande som får hanteras manuellt.

```md
git pull
```
___

## Exempel på arbetsgångar
### Klona ett repo, lägg till branch och gör en pull request 


#### Steg 1 
Skapa en lokal mapp som du kan arbeta i, och därefter mappen.

#### Steg 2 
Klona aktuellt repo så att du har en lokal arbetskopia.

```markdown
git clone https://github.com/andsju/Example
```
Kontrollera att status är korrekt.
```markdown
git status
```
(Visas en annan status, kontrollera att du är i rätt mapp. Du kan byta mapp med kommandon cd, *change directory*)

Skapa en ny branch, ex med namnet '*feature1*'
```markdown
git branch feature1
```
Växla till branch feature1

```markdown
git checkout feature1
```
* Skapa en fil, ex 'headings.md'
* Redigera filen

Lägg till filen så att den versionhanteras, beskriv förändringen och pusha till repot
```markdown
git add headings.md
git commit -m "Added file headings.md"
git push -u origin feature1
```
#### Steg 3 
Nu kan du skapa en pull request på GitHub. 
* Visa det repo på Github dit branchen pushades
* Kontrollera att du ser din branch, klicka på branch
* Leta efter valet 'Pull request'
* Ange en kommentar för Pull request

___

GitHub https://andsju.github.io/GitCMDs/