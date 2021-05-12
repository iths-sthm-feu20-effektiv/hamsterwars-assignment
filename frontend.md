# HAMSTERWARS frontend

+ [Backend](backend.md): REST API med Node.js, Express och Firestore
+ Frontend: web app med React

Frontend-uppgiften handlar om att bygga en app, som använder backend

---
## Specifikation
Hamster-objekt och match-objekt finns beskrivna i [backend.md](backend.md).

---
#### Godkänt-nivå
Appen ska ha ett följande vyer:

|Vy         |Frontend route |Innehåll |
|-----------|---------------|---------|
|Startsida  |`/`            |Förklara hur man använder appen. |
|Tävla      |`/battle`      |Visa två slumpade hamstrar. Låt användaren välja den sötaste. Visa resultatet och initiera nästa match. |
|Galleri    |`/gallery`     |Visa alla hamstrar som finns i databasen. Från galleriet ska man även kunna lägga till nya hamstrar och ta bort gamla. |
|Statistik (**VG**)  |`/statistics` |Visa de 5 hamstrar som vunnit respektive förlorat mest. |
|Historik (**VG**)  |`/history` |Visa resultatet från de senaste matcherna. Ta bort resultat. |


##### Startsida
Här ska du förklara för användaren hur man använder appen. Länka till vyerna *Tävla* och *Galleri*. (Med React Router-länkar, `<Link />`.)

Om det av någon anledning inte går att nå backend-servern så ska du visa ett användarvänligt felmeddelande här. Användaren ska också få möjligheten att försöka igen.


##### Tävla
När battle-vyn visas ska du slumpa två hamstrar och visa dem. Användaren ska klicka på den sötaste. Man ska kunna se bilderna och information om varje hamster - men inte hur många vinster/förluster hamstern har. (Det kan påverka hur man röstar!)

När användaren klickar ska båda hamster-objekten uppdateras: vinnaren får +1 vinst och förloraren +1 förlust. Nu ska du visa hur många vinster och förluster respektive hamster har. Användaren ska få möjligheten att starta en ny match, med två slumpade hamstrar.

##### Gallery
Här ska appen visa alla hamstrars namn och bild, i ett CSS grid. (Visa inte för mycket information direkt, utan låt användaren klicka/hovra över en bild för att visa mer information.)

Man ska kunna ta bort en hamster från galleriet.

Man ska kunna lägga till en ny hamster via ett formulär. Formuläret ska använda validering.


---
#### VG-nivå

##### Galleri
Förutom G-nivån ska man kunna välja en hamster, och se vilka den har besegrat. (`/matchWinners`)

##### Statistik
Visa de 5 hamstrar som vunnit mest, och de 5 hamstrar som förlorat mest.

##### Historik
Visa resultatet från de senaste matcherna: bild och namn för både vinnare och förlorare.


---
#### Level ups
1. Live-chat med andra som använder din app! Man kan prenumerera på uppdateringar från Firestore med metoden onSnapshot. Använd Firestore i frontend. https://firebase.google.com/docs/firestore/query-data/listen

Från backend:
1. GET /defeated/:hamsterId - array med id för alla hamstrar den valda hamstern har besegrat
1. GET /score/:challenger/:defender - två hamster-id som parameter. Respons ska vara ett objekt { challengerWins, defenderWins } med antal vinster för respektive hamster, när de har mött varandra.
1. GET /fewMatches - returnerar en array med id för de hamstrar som spelat minst antal matcher. Arrayen ska ha minst ett element.
1. GET /manyMatches - returnerar en array med id för de hamstrar som spelat flest antal matcher. Arrayen ska ha minst ett element.

TODO

---
## Bedömning och återkoppling
TODO

---
## Inlämning
Du ska lämna in på ITHS distans: ditt repo och länkar till GitHub och din publicerade app. Observera att repot måste vara *publikt* för att inlämningen ska kunna bedömas.

Du kan dessutom redovisa appen för läraren på handledningstid, för att få en snabbare bedömning och feedback.

1. ladda upp repot som en zip-fil
2. skriv de två länkarna
3. skriv om du har gjort några level ups, eller om du vill ha feedback på något särskilt

Exempel - så här ska du skriva länkarna:
```
GitHub: https://github.com/iths-sthm-feu20-effektiv/hamsterwars-assignment
Publicerad: https://my-hamsterswars-submission.herokuapp.com
```
