<h1>SRP prototype overhoorbot</h1>
Versie 3. 20 april 2018<br>
Y.Westplat<br>
y.westplat@hva.nl<br>
<hr> 

<h3>Chatbot productie Tools</h3>

Google Dialogﬂow https://dialogﬂow.com/

Google Actions templates (met google docs koppeling) 
https://developers.google.com/actions/templates/

<b>Voorbeeld met overhoren</b>
https://developers.google.com/actions/templates/flash-cards

Flow.ai lijkt op chatfuel, maar heeft meer kanalen en mogelijkheden voor voice https://ﬂow.ai/

Bot Society (interessante combi van prototyping + json export) https://botsociety.io

Chatfuel http://chatfuel.com

<hr>
<h3>Opdracht</h3>
<p>Maak een werkend prototype voor een chatbot (text) voor één of meerdere messenger- platformen OF een web interface, waarmee kinderen een woordenlijst kunnen overhoren, en docenten de lijst kunnen samenstellen. Lever de instructies waarmee iedereen je aanpak kan navolgen.</p>

<h4>Deliverable SRP</h4>
<p>Applicatie met alle functionerende intents, (of gedeeltelijk werkend, met plan van aanpak voor de ontbrekende intents)</p>
<p>Navolgbare instructies (iemand kan de bot met jouw instructies maken) Source en korte beschrijving architectuur</p>
<p>Oplevering op een publieke GitHub depository</p>

<h4>Aanleiding</h4>
<p>In HvA CMD onderzoeken we de (on)mogelijkheden van de conversational interface en ontwikkelen we een lesmethode voor conversational interface design. In dit experiment testen we het coachen van leerprocessen met een prototype voor de basisschool. Leerlingen willen zelf in hun eigen tijd oefenen met een coach die ze helpt met de voortgang. Docenten in het BO en WO zoeken flexibele, en goedkope manieren om stof te kunnen overhoren.</p>

<h4>Voorbeeld</h4>
<p>Met Google Actions kan iedereen zelf de content van een voice en chatbot maken. Zie https://developers.google.com/actions/templates/
De overhoorbot lijkt een beetje op de Flash Cards action is een voice versie van het spelletje “hints�?, en gebruikt google docs als CMS. Zie de voorbeeldpagina’s voor o.a. con�?guraties https://developers.google.com/actions/templates/ﬂash-cards </p>

<h4>Waarom een chatbot</h4>
<p>Kinderen en jongeren brengen meer tijd door op mobiel dan op desktop of laptop, en gebruiken chat meer dan apps. Chat is een persoonlijke, directe manier van communicatie die direct aansluit op de leefwereld van het kind. Overhoren van huiswerk en de planning van overhoringen levert veel wrijving en stress op bij kinderen. Ouders hebben weinig tijd en daardoor geduld, hebben soms te weinig kennis om hun kinderen te helpen.</p>

<h4>Leren om te leren op de basisschool</h4>
<p>Op de basisschool is het leren van woordjes een middel om de kinderen te leren leren. Het doel is niet direct het leren van een vreemde taal, maar juist het zelfstandig plannen, leren en reﬂecteren.</p>

<h4>Oplossing</h4>
<ul>
  <li>Onze bot laat kinderen zichzelf te overhoren. Het gaat hierbij vooral om het “stampen�?: overhoren van woordjes in een vreemde taal, of topografie.</li>
<li>Wij laten docenten hun eigen overhoorlijsten maken. De leerling kan via de bot de goede lijst selecteren.</li>
<li>Onze bot laat kinderen overhoringen plannen. Zij zetten een datum, en de bot geeft en suggestie van het aantal overhoringen en stuurt n.a.v. het resultaat reminders</li>
<li>Onze bot laat kinderen zelf hun doelen stellen De bot gaat uit van (% fout) en stelt daarmee doelen vast).</li>

<h4>Demo via bot society</h4>
https://app.botsociety.io/s/5a95245d654221000b3a9910?p=86a144046a75d2f4f8a074cf4a560e9f6e2cd1f7

<h4>Functionele beschrijving prototype</h4>
<p><b>MVP</b> = applicatie waarmee leerlingen zichzelf kunnen overhoren en docenten een lijst kunnen samenstellen
Voor MVP zijn de intents [overhoren] en intent [woordenlijst] zijn noodzakelijk.</p>

Rood = nice to have, buiten MVP<br>
<br>
Intent: [personalisatie]<br>
Bewaart telefoonummer, contact of social media van de gebruiker als [ID] Vraagt [voornaam]<br>
personaliseert op [ID] en [Voornaam].<br>
Intent: [overhoren]<br>
Bot toont beschikbare [woordenlijst]. Er kunnen meerdere woordenlijsten bestaan. Selectie woordenlijst op [titel] en [naam docent]<br>
Gebruiker kiest lijst, bevestigt keuze Bot maakt en bewaart [sessie]<br>
Bot toont in random volgorde één vraag uit een woordenlijst van [N] woorden.<br>
Gebruiker tikt exact het antwoord in. Bot vergelijkt beide versies. De bot onthoudt het [resultaat]. Bij goed toont de bot een aanmoediging, en de volgende vraag
Bij fout start [fout antwoord]<br>
Einde [overhoren] zodra alle woorden goed zijn ingevuld.<br>
Bot toont [resultaat] gebaseerd op hoeveelheid [fout antwoord]<br>
Herhaalt / vraagt aan na het laatste woord van de lijst alle [fout antwoord] opnieuw Stopt [overhoren] zodra alle woorden goed zijn ingevuld.<br>
Bewaart resultaat [overhoren] bij [ID]<br>

Intent : [fout antwoord loop]<br>
Bij 1 x [fout] toont de bot een foutmelding Stelt opnieuw de vraag.<br>
Bij 2 x [fout] toont de bot een foutmelding een geeft het juiste antwoord. De gebruiker moet het juiste antwoord intikken.<br>
Bij goed toont de bot de vraag opnieuw, en vraagt het juiste antwoord in te tikken Bij goed gaat de gebruiker naar de volgende vraag <br>[overhoren]<br>
Intent: [woordenlijst]<br>
Docenten moeten zelf meerdere woordenlijsten kunnen maken en wijzigen. Dit is in het voorbeeld een google docs sheet, maar kan ook een andere vorm hebben.<br>

Voorbeeld template Franse woordjes<br>
Google Action https://developers.google.com/actions/templates/flash-cards<br>
[woordenlijst] aanmaken vraag invoeren en bewaren antwoord invoeren en bewaren follow-up opmerkingen goed / fout woordenlijst activeren
configuratie / parameters woordenlijst: [titel] ("engels naar nederlands�?)<br>
[unieke naam of url lijst] [naam school]<br>
[naam klas] [naam docent] [aantal vragen] [datum] datum toets<br>
[normering]<br>
niveau klas (basisschool, vmbo, havo, vwo) methode<br>

hoofdstuk<br>
[Normering] bepaalt het uiteindelijke cijfer basisschool 65% goed is 6,0
een vergeten of verkeerd accent op een woord - 0,25 fout een spelfout (maar het woord is nog wel herkenbaar) 0,5 fout het woord écht fout/niks ingevuld een hele fout. 1 fout


