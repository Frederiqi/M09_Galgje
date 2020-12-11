# M09_Galgje

## Opdracht: Debug React-Galgje
Je krijgt 6 x een Galgje-applicatie gemaakt met React.

In elke versie zit een bug en een korte omschrijving van de bug.
Gebruik je debug-skills om de fout te achterhalen en te fixen
Schrijf per bug stap voor stap op wat je doet om de bug te achterhalen.

Om een applicatie te installeren neem de volgende stappen:

$git clone de git repository van Winc Academy in een nieuwe directory (map) op je computer
$cd  in deze nieuwe map selecteer je het mapje van  die je wilt oplossen (bijvoorbeeld in het geval van de eerste oefening: $cd HangmanReact-exercise-1/  )
in deze nieuwe directory doe je npm install en dan npm start
je kunt de applicatie nu open op http://localhost:3000

En het probleem is....

* Bug exercise 1: als het woord goed geraden is, verlies je alsnog

* Bug exercise 2: we kunnen geen letter raden

* Bug exercise 3: als we het spel starten is het meteen gewonnen

* Bug exercise 4: als het input veld leeg is dan kunnen we alsnog die "letter" raden

* Bug exercise 5: je kan blijven raden tot -1 guesses

* Bug exercise 6: je kunt dezelfde letter meerdere keren raden  (let op: dit is een nieuwe feature!) 


Werkwijze oefening 1:
* Opzoeken welke component verantwoordelijk is voor weergave bericht dat je wint of verliest.
* Controleren vd variabele die bepaalt welk bericht getoond wordt.
* De functie opzoeken die verantwoordelijk is voor toewijzen waarde en kijken of deze juist en volledig is.
* Checken of het doorgeven van parent naar child goed ging, dit ging niet goed. Namen gechecked in App.js. Er bleek op lijn 15 een typefout te staan in de naam van wordGuessed (er stond wordGuesed)
* Typefout hersteld. Probleem opgelost.

Werkwijze oefening 2:
* Opzoeken of de submit handler goed functioneert.
* Probleem gevonden in lijn 50 van AppContainer.js. Een typefout in guesedLetters, dit moest guessedLetters zijn.
* Typefout hersteld. Probleem opgelost.

Werkwijze oefening 3:
* Inspecteren met DevTools. GameOverProp staat op true in text input.
* Opzoeken op welke plek in de code dit gebeurt.
* Dit blijkt in de functie wordGuessed te zijn in App.js.
* De functie blijkt altijd true als return te geven en dat klopt natuurlijk niet.
* Probleem opgelost door een ! toe te voegen aan het begin van lijn 18.

Werkwijze oefening 4:
* Terugzoeken vanaf submit.
* In AppContainer.js stond geen goede validatie voor het aanpassen van de counter.
* Extra statement toegevoegd in lijn 46 en dit lost het probleem op.

Werkwijze oefening 5:
* In App.js blijkt het betreffende if statement niet juist.
* Aangepast op lijn 30, >= ipv >. Probleem opgelost.

Werkwijze oefening 6:
* In AppContainer.js de functie guessLetterHandler checken.
* Op lijn 48 een check toegevoegd worden en dit lost het probleem op.
