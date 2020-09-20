# Git kommandon


## Nytt repo

##### Remote
Skapa ett nytt repo på github.com. Exempel, ett repo med namnet "GitCMDs".
När ett repo är skapat finns en remote referens som kan anges lokalt i din dator. 
Exempel:

`git remote add origin https://github.com/andsju/GitCMDs.git`

##### Local
Skapa en ny mapp för ditt repo i din dator. Tips är att använda samma namn som det repo du skapat på GitHub. 

Förbered mappen för versionshantering:

```javascript
git init
```
Lägg till det repo som ska finnas på GitHub  
```javascript
git remote add origin https://github.com/andsju/GitCMDs.git
```


Skapa en fil i mappen så att den kan versionhanteras. Exempelvis en fil med namnet "index.html". Lägg till filen i Git:

```javascript
git add index.html
```

För att lägga till flera filera nvnder du en punkt:

```javascript
git add .
```

När du redigerat din fil använder du kommandot git commit för att markera den redo för att visas i molnet. Med växeln -m anger du en kort förklaring på förändring,

```javascript
git commit -m "First commit"
```

Visa din lokala version i molnet:
```javascript
git push origin master
```


