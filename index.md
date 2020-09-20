# Git kommandon
Gudien förutsätter att du har installerat programvaran Git.
___
### Skapa ett nytt repo
I din dator:
* Skapa en ny mapp
* Öppna mappen  

Ange kommandot

```javascript
git init
```
Nu har du skapat ett lokalt **git repo**. En dold mapp med namnet  __.git__ bevakar innehållet i mappen. 

___


### Koppla ett lokalt repo till en server 

```javascript
git remote add origin <server>
```
___


### Klona ett repo
Skapa en kopia av ett repo med kommandot:
```javascript
git clone <server>
```
___


### Lägg till innehåll

Skapa en ny fil i ditt lokala git repo.
Lägg till filen i versionshantering:

```javascript
git add index.html
```

För att lägga till alla filer i mappen ange en punkt:

```javascript
git add .
```

När filen (filer) lagts till (redigerats) ska förändringar markeras som redo för överföring. Det görs med kommandot commit, där växeln -m beskriver förändringen.

```javascript
git commit -m "First commit"
```

### Skicka innehåll till server
Skicka innehållet som finns din lokala version med kommandot push
```javascript
git push origin master
```
___

### Skapa en ny branch
I Git är **master** den branch som allt utgår ifrån. Att lägga till en branch är ett sätt som möjliggör en eventuell förändring. Förändringen kan senare integreras (mergas) med master.

För att skapa en ny branch anges ett namn, ex fix1 
```javascript
git branch fix1
```
En branch aktiveras med checkout:
```javascript
git checkout fix1
```
Visa branches med 
```javascript
git branch
```


## Exempel på arbetsgångar
Klona ett repo, lägg till branch, pusha branch, gör en pull request 
repo: https://github.com/andsju/GitCMDs

### Steg 1 
Skapa lokal mapp och klona repot så att du har en lokal arbetskopia

```javascript
git clone https://github.com/andsju/GitCMDs
```
Kontrollera att status är korrekt, att du är i rätt mapp
```javascript
git status
```

Skapa branch 'perhaps'
```javascript
git branch perhaps
```
Växla till branch 'perhaps'

```javascript
git checkout perhaps
```
Lägg till en fil, ex 'headings.md', beskriv förändringen och pusha till repot
```javascript
git add headings.md
git commit -m "Added file headings.md"
git push -u origin perhaps
```
Gå till det GitHub repo dit branchen pushades
