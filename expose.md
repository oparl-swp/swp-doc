# Exposé

## Ausgangssituation, Projektumfeld und Projektziel

OParl ist ein offener Standard für parlamentarische
Informationssysteme, der sich noch in Entwicklung befindet und
voraussichtlich Anfang Juni verabschiedet wird. In einem
parlamentarischen Informationssystem wird unter anderem gespeichert,
welche Politiker den Ausschüssen angehören; zudem werden dort die
Sitzungsprotokolle und die zugehörigen Drucksachen vorgehalten. Diese
Informationen sind öffentlich, werden in der Regel aber nicht in einem
maschinenlesbaren Format, sondern nur auf einer Webseite zur Verfügung
gestellt. Mit OParl soll man diese Daten auch mit einer
standardisierten JSON-API abfragen können.

Mit unserem Softwareprojekt wollen wir einen OParl-Validator
bauen. Der Validator soll prüfen, ob ein Informationssystem den
Standard richtig umgesetzt hat, ähnlich einem HTML-Validator.
Die Entwicklung eines Validators war von den OParl-Entwicklern von
vornherein vorgesehen. Wir wurden aus dem näheren Entwicklerumfeld
gefragt, ob wir ihn im Rahmen eines Softwareprojekts realisieren wollen.

Wir wollen den Validator als Library programmieren und darauf aufbauend
eine Konsolenanwendung und einen Webservice.

**Die Konsolenanwendung** ist hauptsächlich für RIS-Entwickler gedacht
und soll bei der Entwicklung einer OParl-Schnittstelle helfen.
Sie soll in der Lage sein den gesamten Datensatz oder eine wählbare Teilmenge
zu testen, zum Beispiel soll man den Testlauf auf Dokumente von
bestimmten Typen begrenzen können und auch eine maximal Anzahl an zu
testenden Dokumenten pro Typ festlgen können. Die Fehlerausgabe soll
das Problem genau beschreiben und eine Lösung vorschlagen. Die Konsolenanwendung
soll leicht installierbar sein, auf allen Plattformen laufen und sich
in bestehende Testsysteme (z.B. Jenkins) einbinden lassen.

**Der Webservice** soll auf der offiziellen OParl Webseite angeboten
werden. Nutzer sollen OParl Instanzen testen lassen können, die Ausgabe soll einem 
Zertifikat gleichen. Mit Hilfe der Testergebnisse soll eine
Übersicht über aktuelle verfügbare Oparl Instanzen erstellt werden.
Bei jedem Testlauf soll auch eine Statistik über die Daten erstellt werden,
unter anderem mit der Information welche empfohlenen Eigenschaften in welchem Umfang
umgesetzt wurden. Weiterhin wollen wir ein paar semantische Tests implementieren,
die über die Spezifikation hinaus gehen, aber Auskunft über die Qualität
der Daten geben können. 

Neben der Entwicklung des Validators wollen wir im Rahmen des
Softwareprojekts auch den bestehenden Referenzserver überarbeiten und
während der Review-Phase den Standard auf Fehler überprüfen und
gegebenenfalls Feedback geben. Weiterhin wollen wir unseren Quellcode
dokumentieren, eine Bedienungsanleitung für den Validator schreiben,
das Datenmodell von OParl visualisieren und Beispieldaten erstellen um 
Entwickler bei der Implementierung einer OParl-Schnittstelle zu 
unterstützen.

## Mitglieder des Projektteams und einschlägiges Vorwissen

Lucas, ist im achten Semester Bachelor Informatik. Er hat gute
Kenntnisse in Webentwicklung und grundlegende Kenntnisse in Python
und Django.

Johannes ist im vierten Fachsemester des Bachelor Informatik und hat
bereits gute Java-Kenntnisse und grundlegende Erfahrung mit Python,
Haskell, Assemblersprache und C.

Telofy (alias Denis Drescher) ist im zweiten Semester des
Informatik-Masters, benutzt seit fast zehn Jahren Python und hat seit
2010 als Backend-Entwickler in drei Firmen gearbeitet, die Python
einsetzen.

Alexander Sulfrian studiert Informatik auf Master und hat schon
vielfältige Programmiererfahrungen. Er programmiert seit vielen Jahren
C++, hat aber auch schon bei größeren Projekten in Python (Mailman 3)
mitgearbeitet. Zur Zeit arbeitet er als Studentische Hilfskraft bei
der ZEDAT und setzt dort hauptsächlich C und Perl zur
Softwareentwicklung ein.

Ronald ist im achten Semester Bachelor Informatik. Er hat bisher keinerlei Kenntniss von Python und setzt sich beruflich und privat zumeist mit der Sprache PHP auseinander.

## Zeitplan und Milestones

Zur Strukturierung und zum Management der Entwicklungsprozesse möchten
wir Kanban benutzen, welches das Prinzip des »Lean Development«
propagiert. Iterationen, wie die Sprints im Scrum, sind somit
optional. Stattdessen wollen wir den Projektablauf durch Milestones
untergliedern, welche je etwa zwei Wochen umfassen sollen.

1. Zwei Wochen nach Projektstart, wollen wir zwei minimale Projekte in
   einer Form haben, die es erlaubt sie zu deployen: die
   Validator-Library wird noch jegliche JSON-Objekte ablehnen, doch
   ihre Interfaces sollen bereits auf das Frontend-Projekt abgestimmt
   sein. Das Frontend-Projekt soll eine minimale Eingabemaske für
   JSON-Objekte zur Verfügung stellen und zur Validierung auf die
   Library zurückgreifen. Auf diese Seite können wir den Product
   Owners bereits Zugriff gewähren.
2. Ein existierender Server, der Testdaten ausliefert, soll erweitert
   worden sein, und der Validator soll bereits grundlegende Tests
   durchführen können. Das Web-Frontend soll derweil
   benutzerfreundlicher sein, ins besondere im Bezug auf die
   Fehlerberichterstattung.
3. Gerade alle syntaktisch korrekten Objekte sollen akzeptiert werden,
   und das Frontend-Projekt soll auch JSONs über HTTP und HTTPS
   abrufen und validieren können.
4. Der Validator soll auch JSON-LD-Referenzen validieren, auch unter
   Beachtung von Weltwissen über die in den JSON-Objekten abgebildeten
   politischen Körper. Das Frontend-Projekt soll Hilfestellungen zur
   Lösung typischer Fehler leisten.
5. Um Hierarchien von Objekten vollständig und stichpunktartig
   validieren zu können, soll ein Crawler eine größere Anzahl von
   JSON-Objekten gezielt abrufen und in Bezugnahme aufeinander
   validieren können.


## Softwaretechnische Methoden

Wir werden unser Projekt agil entwickeln. Dafür werden wir Kanban
einsetzen. Im Gegensatz zu Scrum, hat Kanban wesentlich weniger Regeln,
wodurch weniger Verwaltungsaufwand nötig ist. Bei Kanban werden die
verschiedenen Aufgaben als so genannte Stories formuliert. Diese
Stories wandern in einer Art Tabelle (dem Kanban-Board) von links nach
rechts. Die einzelnen Spalten repräsentieren dabei den Stand der
Bearbeitung. Wenn die Aufgabe rechts angekommen ist, ist die Aufgabe
fertig. Jeder Entwickler kann dabei selber entscheiden, welche Story
er als nächstes bearbeitet. Zur Verwaltung unseres Kanban-Boards werden
wir eine Webanwendung, wie zum Beispiel Trello, nutzen. Dies hat den
Vorteil, dass kein Einrichtungsaufwand für die Software anfällt und
sie sofort von allen Teammitgliedern im Browser genutzt werden kann.

Wir werden versuchen so weit wie möglich Test-getrieben zu
entwickeln. Im *test-driven development* werden zuerst die Tests für die
Software geschrieben, die zu Beginn erst einmal fehlschlagen. Erst
danach wird dann eine Implementierung geschrieben, damit die Tests
erfolgreich durchlaufen. Dies wird für den Teil der
Validator-Library relativ einfach sein. Dort müssen wir größtenteils
die Testdaten, die wir validieren wollen, anhand der Spezifikation
erstellen, da der vorhandene Referenzserver nur sehr rudimentär Daten
liefen kann. Im Gegensatz dazu, wird es bei der Webanwendung wesentlich
schwieriger sein, alle Teile Test-getrieben zu entwickeln. Viele Teile
der Webanwendung werden eine graphische Schnittstelle betreffen, und
sind daher schwer zu testen.

Wie bei Projekten, bei denen mehrere Personen zusammenarbeiten, üblich,
werden wir zur Zusammenarbeit ein Versionskontrollsystem
einsetzen. Wir haben uns für GitHub entschieden, da sich dieses in den
letzten Jahren in vielen Bereichen durchgesetzt hat. Außerdem ist mit
GitHub eine Plattform verfügbar, die es ermöglicht den Sourcecode
einfach öffentlich verfügbar zu machen. Unsere ganze Entwicklung kann
dort auch mitverfolgt werden. Die Oparl-Spezifikation wird außerdem
ebenfalls auf GitHub entwickelt, so dass dort Synergie-Effekte
ausgenutzt werden können.


## Anspruchsvolle Informatiktechniken

In unserem Projekt müssen wir verschiedene Techniken verwenden. Unter
anderem müssen wir die OParl-Daten validieren. Dies muss auf mehreren
Wegen geschehen. Einerseits muss überprüft werden, ob die Daten
syntaktisch korrekt sind und dem OParl-Schema entsprechen. Dieser
Schritt kann mit Hilfe einer Bibliothek zur Validierung von
JSON-Schemata gelöst werden. Andererseits müssen die Daten aber auch
auf semantische Korrektheit geprüft werden. Diese beinhaltet neben der
Korrektheit von Verweisen innerhalb von JSON-LD auf andere Objekte,
auch die Validierung von logischen Randbedingungen. Diese können nur
mit dem entsprechenden Wissen validiert werden und können nicht, oder
nur schwer, in einem JSON-Schema abgebildet werden.

Für den umfassenden Test von einer echten Implementierung des
OParl-Standards werden wir alle vorhanden JSON-Dokumente von dem
Server abrufen müssen. Da es keine Liste mit einem Verweis auf alle
Daten gibt, müssen diese Daten mit einem Crawler abgerufen
werden. Über den Einstiegspunkt müssen alle rekursiv verfügbaren
Referenzen abgerufen werden. Dabei muss unter anderem darauf geachtet
werden, dass Verweise auf bereits abgerufene Daten nicht erneut
geladen werden müssen.

Eine wichtige Funktion wird der Webservice darstellen. Um den Validator
möglichst einfach verfügbar zu machen, soll eine Webanwendung
entstehen, die es ermöglicht einen erreichbaren OParl-Server zu
testen. Die Webanwendung soll eine URL entgegennehmen können
und die Daten validieren. Letztlich soll sie die Ergebnisse
übersichtlich darstellen. Die Schnittstelle des Webservices wird dabei
vermutlich anhand des REST-Standards implementiert. Da für eine
umfassende Validierung der Crawler verwendet wird, muss darauf
geachtet werden, dass ein Durchlauf länger dauern kann. Daher muss
auch der spätere Zugriff auf die Ergebnisse möglich sein ohne einen
neuen Durchlauf starten zu müssen. Es soll auch eine Statistik über die
vom getesteten System implementierten empfohlenen Eigeschaften
ausgegeben werden.


## Rollen und Zuständigkeiten

Durch Kanban gibt es kaum feste Rollen, da sie flüssig neu eingenommen
werden, je nachdem welchen Task ein Entwickler wählt.

Es wird jedoch einige De-Facto-Rollen in der Form geben, dass Lucas als
Kundenkontakt fungiert und Telofy, durch seine langjährige Erfahrung
in der Entwicklung mit Python, die passenden Libraries und Frameworks
auswählt.


## Sprachen, Frameworks und Werkzeuge

- Den Validator wollen wir in Python 2 mit Support für Python 3 entwickeln
- Für die Validierung wollen wir JSON Schema und JSON-LD Kontexte verwenden
- Als Webframework wollen wir Flask, zusammen mit Circus verwenden
- Als Buildtool wollen wir Buildout verwenden
- Zur Quellcodeverwaltung wollen wir Git benutzen


## Kundenkontakt

Unsere Kunden sind die OParl-Entwickler. Da sie nicht aus Berlin
kommen werden wir voraussichtlich per E-Mail oder
Telefon kommunizieren. Zum Beginn unseres Softwareprojekts wollen wir
ihnen unseren Plan schicken und uns Feedback einholen. In den nächsten
Wochen wird OParl in die Review-Phase kommen. Während dieser Zeit
werden wir unser Feedback und verbleibende Fragen zur Spezifikation
schicken. Anschließend werden wir die Entwickler voraussichtlich zu
jedem Meilenstein über den aktuellen Stand informieren. 


## Risikomanagement

Aufgrund der Tatsache, dass die zu validierende Norm noch nicht
fertig gestellt ist, wird das Hauptrisiko dieses Projekts sein, dass
die  Spezifikation noch geändert werden könnte und der bereits
ausgearbeitete  Teil der Software angepasst werden müsste. Um dieses
Problem abzumildern, wollen wir bis Oparl die Version 1.0 erreicht,
ausschließlich grundlegende Funktionen und Tests implementieren. Da
die Tests unseres Validators für zukünftige OParl-Versionen leicht
anpassbar sein sollen, werden unerwartete Änderungen zeitlich nicht zu 
schwer in Gewicht fallen.

Außerdem soll rege Kommunikation mit den Kunden dazu beitragen, dass
wir auf dem aktuellen Stand sind und über zukünftige Änderung in der
Spezifikation informiert werden.


## Anforderungen an die Validierung

Wir versuchen einen Großteil der Dokumente mit von uns definierten 
JSON-Schemas und JSON-LD Kontexten zu testen. Folgende notwendigen oder 
empfohlenen Eigenschaften können nicht überprüft werden und müssen 
zusätzlich getestet werden:

### Zu testende Servereigenschaften

- **Paginierung:** Bei Listen mit mehr als 100 Einträgen wird 
Paginierung empfohlen. Bei einer Paginierung muss jede Seite (bis auf 
die letzte) gleich viele und maximal 100 Einträge enthalten. Die 
Seiten müssen, anders als Dokumente, mit den in RFC5988 beschriebenen 
HTTP-Headern verlinkt werden. Jede Seite muss mit der jeweils 
nächsten Seite verlinkt sein, optional darf sie auch mit der 
vorherigen, ersten und letzten Seite verlinkt sein. Falls eine Liste, 
die direkt als Wert in einem Objekt gespeichert ist, mehr als 100 
Einträge enthält, soll sie über eine eigene URL angeboten werden.

- **Eindeutige URLs:** Jedes Dokument darf nur unter einer URL 
angeboten werden, dabei sind alle Bestandteile einer URL betroffen: 
ein Dokument darf also entweder unter http oder https erreichbar sein 
und selbst bei einer Vertauschung der Query-Parameter Reihenfolge 
darf nicht das selbe Dokument ausgeliefert werden, eine Weiterlung 
mit Statuscode 301 ist aber zulässig.

- **JSONP:** Es ist empfohlen JSONP anzubieten, der aktivierende 
Parameter muss callback heißen, der Wert darf aus Sicherheitsgründen 
nur aus Buchstaben und Zahlen bestehen, ansonsten muss mit Statuscode 
400 geantwortet werden.

- **Feeds:** Ein Server soll die Feeds "Neue Objekte", "Geänderte 
Objekte" und "Entfernte Objekte" anbieten. Die Feeds müssen umgekehrt 
chronologisch sortiert sein und es ist empfohlen, dass sie mindestens 
einen Zeitraum von 365 Tagen abdecken. Wenn ein neues Objekt erstellt 
wird, gilt es nicht als Änderung, es darf nur im Feed "Neue Objekte" 
erscheinen, Dopplungen sind nicht erlaubt.

- **Richtige Header bei Dateidownloads:** HTTP-HEAD muss für 
Dateianfragen unterstützt werden und es muss ein Last-Modified-Header 
mitgeschickt werden, empfohlen sind die Header "Content-Length" und 
"ETag", weiterhin ist es empfohlen "Conditional GET" mit den 
Parametern If-Modified-Since und If-None-Match anzubieten. Es darf 
auch mit einer Weiterleitung geantwortet werden, je nach Situation 
mit Statuscode 301 oder 307, bei nicht mehr vorhandenen Dateien soll 
mit 410 geantwortet werden. Bei einer Dateianfrage über die 
Download-URL muss der Server einen Content-Disposition Header senden 
mit dem Typ "attachment" (im Gegensatz zur Anfrage über die 
Zugriffs-URL) und dem filename-Parameter. Der Dateiname soll das 
angefragte Dokument beschreiben (also nicht immer gleich sein), ein 
Name aus ASCII Zeichen ist empfohlen. 

- **Kompression:** Server sollen mindestens eines der 
Kompressionsverfahren gzip, compress oder deflate unterstützen und 
verwenden, falls ein Client mittels Accept-Encoding-Header diese 
anfragt. Bereits komprimierte Dateien, wie PDF, dürfen jedoch immer 
in einer unkomprimierten HTTP-Antwort übertragen werden. 

- **Passende Statuscodes:** Bei ungültigen Anfragen, sollen die 
entsprechenden HTTP 1.1 Statuscodes ausgegeben werden, unter anderem: 
400 (Bad Request), 404 (Not Found) oder 405 (Method Not Allowed). 


### Zu testende Dokumenteigeschaften

- **Richtige Links:** Links müssen zum erwartete Dokumenttyp zeigen. 
Viele Dokumenttypen müssen doppelt miteinander verlinkt werden, zum 
Beispiel wenn eine Sitzung Tagesordnungspunkte verlinkt, muss 
jeder Tagesordnungspunkt zur zugehörigen Sitzung zurück verlinkt sein.

- **Geodaten:** Geodaten müssen im "Well-Known-Text-Format" (WKT) 
angegeben werden und Koordinaten dürfen nur im WGS84 System angegeben 
werden.

- **SKOS:** Bei manchen Dokumenten kann SKOS-Vokabular (Simple 
Knowledge Organization System) definiert und in anderen Dokumenten 
verwendet werden. Zum Beispiel können in einem Ausschuss, Rollen 
angegeben werden, die dann den Mitgliedern zugewiesen werden können.

- **nicht spezifizierte Eigenschaften:** Jedes Dokument darf 
zusätzlich nicht von OParl spezifizierte Eigenschaften besitzen. 
Solche Eigenschaften wollen wir erkennen und mit in die Statistik 
aufnehmen.

- Es gibt noch ein paar weitere Eigenschaften, die sich nicht mit 
einem Schema überprüft werden können. Zum Beispiel muss es genau ein 
Dokument vom Typ "oparl:System" geben, manche Eigenschaften haben 
Abhängigkeiten (zum Beispiel name und nameLong dürfen nicht identisch 
sein), bei Dateien müssen die angegebene Eigenschaften passen 
(Checksumme, Mimetype und Größe) und die Eigenschaft @id muss immer 
der URL entsprechen.



## Benotung

Wir schlagen vor die Benotungen in Form einer individualisierten
Gruppennote zu gestalten. Die Gruppe soll zuerst als Ganzes bewertet
werden, um die Zensuren anschließend individuell an den Arbeitsumfang
und die Komplexität der Aufgabenbereiche jedes Einzelnen
anzupassen. Die Individualisierung soll mit Hilfe eines Meetings
zwischen den wissenschaftlichen Mitarbeitern und den Teilnehmern des
Softwareprojekts erleichtert werden. Durch die, von den
Projektteilnehmern ausgearbeitete Dokumentation, welche detaillierte
Informationen über die Arbeiten der einzelnen Projektteilnehmer
enthält, wird eine fundierte Bewertung der einzelnen Teilnehmer durch
den zuständigen Professor und seine wissenschaftlichen Mitarbeiter,
gefördert.
