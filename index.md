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

## Exempel på arbetsgångar