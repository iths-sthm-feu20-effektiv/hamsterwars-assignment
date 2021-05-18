# HAMSTERWARS frontend

+ [Backend](backend.md): REST API med Node.js, Express och Firestore
+ Frontend: web app med React

Frontend-uppgiften handlar om att bygga en app, som använder backend från första uppgiften.

---
## Specifikation
Hamster-objekt och match-objekt finns beskrivna i [backend.md](backend.md).

---
#### Godkänt-nivå
Först ska du skriva i `README.md` om vad du har jobbat med.

Appen ska ha följande vyer:

|Vy         |Frontend- route |Innehåll |
|-----------|---------------|---------|
|Startsida  |`/`            |Förklara hur man använder appen. |
|Tävla      |`/battle`      |Visa två slumpade hamstrar. Låt användaren välja den sötaste. Visa resultatet och initiera nästa match. |
|Galleri    |`/gallery`     |Visa alla hamstrar som finns i databasen. Från galleriet ska man även kunna lägga till nya hamstrar och ta bort gamla. |
|Statistik (**VG**)  |`/statistics` |Visa de 5 hamstrar som vunnit respektive förlorat mest. |
|Historik (**VG**)  |`/history` |Visa resultatet från de senaste matcherna. Ta bort resultat. |


##### Startsida
Här ska du förklara för användaren hur man använder appen. Länka till vyerna *Tävla* och *Galleri*. (Med React Router-länkar, `<Link />`.)

Om det av någon anledning inte går att nå backend-servern så ska du visa ett *användarvänligt felmeddelande* här. Användaren ska också få möjligheten att försöka igen.


##### Tävla
När battle-vyn visas ska du slumpa två hamstrar, som visas för användaren. Användaren ska klicka för att rösta på den sötaste. Man ska kunna se bilderna och information om varje hamster - men inte hur många vinster/förluster hamstern har. (Det kan påverka hur man röstar!)

När användaren klickar ska båda hamster-objekten uppdateras: vinnaren får +1 vinst och förloraren +1 förlust. Nu ska du visa hur många vinster och förluster respektive hamster har. Användaren ska få möjligheten att starta en ny match, med två slumpade hamstrar.

*Tänk på att uppdatera alla dokument i databasen där vinst och förlust lagras.*


##### Galleri
Här ska appen visa alla hamstrars namn och bild, i ett CSS grid.

Man ska kunna ta bort en hamster från galleriet.

Man ska kunna lägga till en ny hamster via ett formulär. Formuläret ska använda validering.

*Tänk på att inte visa för mycket information direkt. Låt användaren klicka/hovra över en bild för att visa mer information.*


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
*Dessa uppgifter är förslag, som är till för dig som vill ha en större utmaning. Skriv i README.md om vilka level ups du gör.*

1. Förhöj användarupplevelsen med animationer.

1. Live-chat med andra som använder din app! Man kan prenumerera på uppdateringar från Firestore med metoden onSnapshot. Använd Firestore i frontend eller socket.io: <br>
https://firebase.google.com/docs/firestore/query-data/listen <br>
https://socket.io/demos/chat/

1. Klicka på en hamster i galleriet, för att se vilka andra hamstrar den har besegrat i tidigare matcher.
<br>Backend-route: `GET /defeated/:hamsterId`

1. Ny sida, **Rivalitet**: användaren ska välja två hamstrar, och kunna se deras inbördes poängställning. Exempel: `Hanna 5 - Herkules 3`.
<br>Backend-route: `GET /score/:challenger/:defender`

1. Ny sida, **Fighters and slackers**: visa de hamstrar som haft flest respektive minst matcher.
<br>Backend-route: `GET /fewMatches` och `GET /manyMatches`


---
## Bedömning och återkoppling
För G krävs:
+ alla vyer på G-nivå finns och fungerar
+ appen är publicerad online
+ korrekt inlämning med zip-fil, länk till repot, och länk till appen

För VG krävs dessutom:
+ alla vyer på VG-nivå
+ appen är snygg och användarvänlig

Redovisa appen på handledningstid sista kursveckan, för att få direkt bedömning och återkoppling.


---
## Inlämning
Du ska lämna in på ITHS distans: ditt repo och länkar till GitHub och din publicerade app. Observera att repot måste vara *publikt* för att inlämningen ska kunna bedömas.

Du kan dessutom redovisa appen för läraren på handledningstid, för att få feedback och en snabbare bedömning.

1. ladda upp repot som en zip-fil
2. skriv de två länkarna
3. skriv om du har gjort några level ups, eller om du vill ha feedback på något särskilt (ja, både på iths distans och i README.md)

Exempel - så här kan du skriva:
```
https://github.com/my-github-username/hamsterwars-fullstack
https://my-hamsterswars-submission.herokuapp.com

Jag har gjort följande level ups: 1, 2, 5.
Jag vill ha återkoppling på min lösning på galleriet, närmare bestämt...
```

*Lycka till!*
