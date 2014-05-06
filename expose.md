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
Standard richtig umgesetzt hat, ähnlich einem HTML-Validator. Er soll
hauptsächlich Entwicklern von parlamentarischen Informationssystemen
bei der Implementierung einer OParl-Schnittstelle helfen. Er soll
weiterhin Nutzern der OParl-API ermöglichen, zu testen, ob die Daten
in einem System noch valide sind. Die Entwicklung eines Validators war
von den OParl-Entwicklern von vornherein vorgesehen. Wir wurden aus
dem näheren Entwicklerumfeld gefragt, ob wir ihn im Rahmen eines
Softwareprojekts realisieren wollen.

Der Validator soll als Konsolenanwendung und mit einem Web-Frontend
benutzbar sein. Er soll einzelne Dokumente, einen Teil oder den ganzen
Datensatz testen können. Er soll optional semantische Tests
durchführen können, die über die Spezifikation hinaus gehen, aber
Auskunft über Fehler in den Daten geben können. Weiterhin soll er eine
Statistik über die validierten Daten ausgeben können, zum Beispiel
welche optionalen, empfohlenen oder nicht spezifierten Angaben in
welchem Umfang enthalten waren.

Neben der Entwicklung des Validators wollen wir im Rahmen des
Softwareprojekts auch den bestehenden Referenzserver überarbeiten und
während der Review-Phase den Standard auf Fehler überprüfen und
gegebenenfalls Feedback geben.


## Mitglieder des Projektteams und einschlägiges Vorwissen

Lucas, ist im achten Semester Bachelor Informatik. Hat gute
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
testen. Die Webanwendung soll eine URL oder ein JSON-Dokument
entgegennehmen können und die Daten validieren. Letztlich soll sie die Ergebnisse
übersichtlich darstellen. Die Schnittstelle des Webservices wird dabei
vermutlich anhand des REST-Standards implementiert. Da für eine
umfassende Validierung der Crawler verwendet wird, muss darauf
geachtet werden, dass ein Durchlauf länger dauern kann. Daher muss
auch der spätere Zugriff auf die Ergebnisse möglich sein ohne einen
neuen Durchlauf starten zu müssen. Eventuell sollte es auch möglich
sein, einzelne Dokumente, die einen Fehler aufwiesen, erneut zu
validieren.


## Rollen und Zuständigkeiten

TODO!

Durch Kanban gibt es kaum feste Rollen, da sie flüssig neu eingenommen
werden, je nachdem welchen Task ein Entwickler wählt.

De-Facto-Rollen:
- Lucas: Kontakt mit Kunden
- Telofy: Python-Fragen


## Sprachen, Frameworks und Werkzeuge

- Python
- Buildout
- Django oder Flask
- Git
- Circus
- JSON/-LD
- Spline Pad
- GitHub


## Kundenkontakt

Unsere Kunden sind die OParl-Entwickler. Da sie nicht aus Berlin
kommen werden wir voraussichtlich voraussichtlich per E-Mail oder
Telefon kommunizieren. Zum Beginn unseres Softwareprojekts wollen wir
ihnen unseren Plan schicken und uns Feedback einholen. In den nächsten
Wochen wird OParl in die Review-Phase kommen. Während dieser Zeit
werden wir unser Feedback und verbleibende Fragen zur Spezifikation
schicken. Anschließend werden wir die Entwickler voraussichtlich zu
jedem Meilenstein über den aktuellen Stand informieren. Unsere
Entwicklung wird auch auf GitHub verfolgbar sein.


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
