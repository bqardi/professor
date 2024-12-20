# Professor Terning

### Hvordan man løser en Rubiks Cube/professor terning.

:scroll:På https://bqardi.github.io/professor/ vil jeg vise dig den nemmeste måde at løse en professor terning/Rubiks Cube på, med udførlige trin for trin forklaringer.

:1st_place_medal:[Min metode](https://bqardi.github.io/professor/my-method.html) -siden indeholder den metode jeg bruger til at løse terningen på, som er lidt mere avanceret end begyndermetoden. Den indeholder også en liste over de algoritmer, jeg personligt bruger/foretrækker sammen med forklaringer på forskellige fingerteknikker og metoder til at blive hurtigere til at løse terningen.

:jigsaw:Du kan også finde et [lille program](https://bqardi.github.io/professor/online-cube.html), jeg har lavet i [Unity](https://unity.com/), hvor du kan prøve at løse en professer terning på tid, ved at pege med musen på en side og så dreje med WASD tasterne på keyboardet (fungerer bedst på stor skærm/desktop og links til denne side er derfor skjult på mobil).

:hourglass_flowing_sand:Jeg har lavet en [timer](https://bqardi.github.io/professor/timer.html), som specifikt er lavet til at måle din tid med en fysisk terning.

- Den indeholder en algoritme-blandings-generator der genererer en tilfældig algoritme du kan bruge til at blande din terning med (denne algoritme bliver "gemt" sammen med dine tidsregistreringer).
- Ifølge officielle regler ved speedcubing konkurrencer har man 15 sekunder til at inspicere terningen før man går i gang med at løse. Derfor har jeg inkorporeret en countdown tæller der tæller ned fra 15 sekunder før tiden går i gang.
  - Tryk i det **blå felt** for at starte **15 sekunders timeren**.
  - Tryk igen i det **blå felt** for at **starte** den egentlige **timer** inden de 15 sekunder er gået.
  - Tryk igen i det **blå felt** for at **stoppe timeren** og registrere tiden.
  - Du kan også bruge **mellemrumstasten** for at **pre-starte**, **starte** og **stoppe** timeren (samme steps som ovenover).
- Der er også en indikator til at sammenligne din nuværende tid med din rekordtid, som vises mens timeren kører (rød gradient box der fader ind og bliver mere og mere tydelig jo tættere du kommer på din rekord tid. Den skifter til komplet rød farve når du overskrider din rekordtid).
- Når man stopper tiden, sammenlignes tiden med dine andre tider og bliver sorteret på en liste over alle dine tider (tryk på :stopwatch: stopur-ikonet for at se listen).
- Man kan også se information om bedste tid og gennemsnitstid, hvis du trykker på :bar_chart: graf-ikonet.

---

### Opbygning

Siden er lavet med semantisk HTML og med ekstern CSS styling.

Hero billedet er tegnet af vores ældste søn, Simon (og er det eneste reele billede der er på samtlige sider), og terningen er udelukkende bygget med CSS. Den er animeret med CSS animations for at dreje den rundt (i 3D space).

JavaScript er benyttet til menuen på mobil, til timeren, til forskellige knapper og så er jeg for nyligt blevet introduceret for [Intersection Observer](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API) (tak [Ronny](https://github.com/ronfrontweb) fordi du fandt dette geniale API).

Intersection Observer er en API der "observerer" eller "holder øje" med HTML-elementerne på siden og når et element "kommer til syne" i viewporten (eller et andet specificeret forældre-element) fyrer observeren en event af.

- Denne event har jeg brugt til at animere mine "CSS konstruerede billeder" ind på plads når man scroller ned til dem.
- Den er også brugt til min To Top knap, som er skjult når man er scrollet helt op til toppen af siden og når man scroller helt ned til footeren, skifter den fra `position: fixed;` til `position: absolute;`, så den ikke "er i vejen" for footeren.
- Og så er den brugt til notations-knappen, som dukker op nede i venstre hjørne, når man scroller forbi notationsforklaringerne på hovedsiden ("Lær at løse").

Jeg har brugt en del energi på den animerede CSS terning, for at få funktionaliteten af at den "følger" musen (tryk pause for at aktivere denne funktion). Jeg var nødt til at bruge en del matematik til beregning og konvertering af musekoordinaterne til rotationsgrader af terningen (koordinater i `px` til `deg` brugt i CSS property'erne `transform: rotateX()` og `transform: rotateY()`).

Held og lykke med løsning af professor terningen.
