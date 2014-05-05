# Exposé

## Ausgangssituation im Projektumfeld, Projektziel (grob)

OParl ist ein offener Standard für parlamentarische Informationssysteme, der sich noch in Entwicklung befindet und voraussichtlich Anfang Juni verabschiedet wird. In einem parlamentarischen Informationssystem wird unter anderem gespeichert, welche Politiker den Ausschüssen angehören, die Sitzungsprotokolle und die zugehörigen Drucksachen. Diese Informationen sind öffentlich, werden in der Regel aber nicht in einem maschinenlesbaren Format, sondern nur auf einer Webseite zur Verfügung gestellt. Mit OParl soll man diese Daten auch mit einer standardisierten JSON-API abfragen können.

Mit unserem Softwareprojekt wollen wir einen OParl-Validator bauen. Der Validator soll prüfen ob ein Informationssystem den Standard richtig umgesetzt hat, ähnlich einem HTML Validator. Er soll hauptsächlich Entwicklern von parlamentarischen Informationssystemen bei der Implementierung einer OParl Schnittstelle helfen. Er soll weiterhin Nutzern der OParl-API ermöglichen, zu testen, ob die Daten in einem System noch valide sind. Die Entwicklung eines Validators war von den OParl Entwicklern von vornherein vorgesehen. Wir wurden aus dem näheren Entwicklerumfeld gefragt, ob wir ihn im Rahmen eines Softwareprojekts realisieren wollen.

Der Validator soll als Konsolenanwendung und mit einem Webfrontend benutzbar sein. Er soll einzelne Dokumente, einen Teil oder den ganzen Datensatz testen können. Er soll optional semantische Tests durchführen können, die über die Spezifikation hinaus gehen, aber Auskunft über Fehler in den Daten geben können. Weiterhin soll er eine Statistik über die validierten Daten ausgeben können, zum Beispiel welche optionalen, empfohlenen oder nicht spezifierten Angaben in welchem Umfang enthalten waren.

Neben der Entwicklung des Validators wollen wir im Rahmen des Softwareprojekts auch den bestehenden Referenzserver überarbeiten und während der Review Phase den Standard auf Fehler überprüfen und gegebenfalls Feedback geben.


## Mitglieder des Projektteams; deren einschlägiges Vorwissen

Lucas, ist im achten Semester Bachelor Informatik. Hat gute
Kenntnisse in Webentwicklung und grundlegende Kenntnisse in Python
und Django.

Johannes ist im vierten Fachsemester des Bachelor Informatik und hat bereits gute Java Kenntnisse und grundlegende Erfahrung mit Python, Haskell, Assemble und C. 

Telofy (alias Denis Drescher) ist im zweiten Semester des Informatik-Masters,
benutzt seit fast zehn Jahren Python und hat seit 2010 als Backend-Entwickler
in drei Firmen gearbeitet, die Python einsetzen. Er hat mehr Erfahrung
mit Python als mit anderen Programmiersprachen, findet aber auch Haskell
ganz flauschig.

- Universitärer Hintergrund
- Beruflicher Hintergrund
- Präferierte Programmiersprachen
- Präferierte Libraries, Frameworks etc. im Bezug auf Python


## Ungefährer Inhalt der Ergebnisse jeder Iteration; Zeitplan dazu
    
Zur Strukturierung und zum Management der Entwicklungsprozesse möchten wir
Kanban benutzen, welches das Prinzip des »Lean Development« propagiert.
Iterationen, wie die Sprints im Scrum, sind somit optional. Stattdessen
wollen wir den Projektaublauf durch Milestones untergliedern, welche je etwa
zwei Wochen umfassen sollen.

1. Zwei Wochen nach Projektstart, wollen wir zwei minimale Projekte in einer
   Form haben, die es erlaubt sie zu deployen: die Validator-Library kann noch
   jegliche JSON-Objekte ablehnen, doch ihre Interfaces sollen bereits auf das
   Frontend-Projekt abgestimmt sein. Das Frontend-Projekt soll eine minimale
   Eingabemaske für JSON-Objekte zur Verfügung stellen und zur Validierung auf
   die Library zurückgreifen. Auf diese Seite können wir den POs bereits
   Zugriff gewähren.
2. Ein existierender Server, der Testdaten ausliefert, soll erweitert worden
   sein, und der Validator soll bereits einfachere Klassen von Objekten
   akzeptieren, dabei aber lediglich syntaktisch evaluieren. Das Frontend-Projekt
   soll derweil benutzerfreundlicher sein, ins besondere im Bezug auf die
   Fehlerberichterstattung.
3. Gerade alle syntaktisch korrekten Objekte sollen akzeptiert werden, und das
   Frontend-Projekt soll auch JSONs über HTTP und HTTPS abrufen und validieren
   können.
4. Der Validator soll dahingehend erweitert worden sein, dass er auch JSON-LD-
   Referenzen validiert, allerdings noch nicht unter Beachtung von Weltwissen
   über die in den JSON-Objekten abgebildeten politischen Körper. Das Frontend-Projekt soll Hilfestellungen zur Lösung typischer Fehler leisten.
5. Weltwissen soll miteinbezogen werden, um zu validieren, ob die abgebildeten
   Strukturen tatsächlich existieren können. (Vielleicht noch etwas erweitern.)
6. Um Hierarchien von Objekten vollständig und stichpunktartig validieren zu können,
   soll ein Crawler eine größere Anzahl von JSON-Objekten gezielt abrufen und in
   Bezugnahme aufeinander validieren können. (Vielleicht noch etwas erweitern.)

- Absatz darüber, dass der Begriff der Iteration auf eine
  Kanban-getriebene Methodologie schwerlich anwendbar ist, aber
- dass wir uns Milestones setzen werden, um Struktur und
  Berechenbarkeit in unsere Prozesse zu bringen.
- Die Milestones
    1. Minimaler Proof-of-Concept des Webinterfaces und der
       Library, das alle JSONs rejectet
    2. Test-Server erweitern und einige bereits vorhandene
       Soll-Daten syntaktisch validieren
    3. Test-Server hübsch machen und syntaktische Validierung
       komplettieren
    4. Syntaktische oder so JSON-LD-Validierung
    5. Semantische Validierung unter Anwendung von Expertenwissens
    6. Crawler
- Etwa zwei Wochen pro Milestone.


## Welche softwaretechnischen Methoden sollen wann wofür wie intensiv
   eingesetzt werden?

- Kanban
- Mehr Stuff


## Welche anspruchsvollen Informatiktechniken sollen wofür eingesetzt
   werden?

- Django/Pyramid
- Buildout


## Welches Mitglied hat welche Rolle oder Zuständigkeit?

- Kanban

Es gibt mehrere Rollen die werden immer wieder neu vergeben.


## Liste von Sprachen, Frameworks, Werkzeugen und Bausteinen, die voraussichtlich eingesetzt werden
    
- Python
- JSON / -LD
- Spline Pad
- Github


## Wie und wie oft wird der Kunde eingebunden?

Unsere Kunden sind die OParl Entwickler. Da sie nicht aus Berlin kommen werden wir vorausichtlich voraussichtlich per EMail oder Telefon kommunizieren.
Zum Beginn unseres Softwareprojekts wollen wir ihnen unseren Plan schicken und uns Feedback einholen. In den nächsten Wochen wird OParl in die Review Phase kommen. Während dieser Phase werden wir unser Feedback und verbleibende Fragen zur Spezifikation schicken. Anschließend werden wir die Entwickler vorausichtlich zu jedem Meilenstein über den aktuellen Stand informieren.
Unsere Entwicklung wird auch auf Github verfolgbar sein.


## Welche Hauptrisiken bestehen für den Erfolg? Wie wird ihre Eintrittswahrscheinlichkeit reduziert oder die Wirkungen des Eintretens beherrscht?

Aufgrund der Tatsache, dass die zu validierende Norm noch nicht fertiggestellt ist, wird das Hauptrisiko dieses Projekts sein, dass die Spezifikation noch geändert werden könnte und der bereits ausgearbeitete Teil der Software angepasst werden müsste. Dies würde sich negativ auf die Zeitplanung des Projekts auswirken. Um dieses Problem abzumildern, sollen deswegen, bis Oparl die Version 1.0 erreicht, ausschließlich grundlegende Funktionen und Tests implementiert werden.

Außerdem soll der Validator, im Fall einer Änderung der Anforderungen, leicht anzupassen sein. Rege Kommunikation mit den Kunden soll dazu beitragen, dass beide Parteien immer auf dem aktuellen Stand der Dinge sind und um Fehler im Anforderungsmanagement schnell und effizient zu erkennen. 

Ebenso wichtig ist, dass die Mitarbeiter untereinander ausreichend kommunizieren, um auf das Ausfallen von Mitarbeitern gut reagieren können. 

Grundlegend ist mangelnde Robustheit, Benutzerfreundlichkeit und Performance ebenfalls ein nicht zu unterschätzendes Risiko, dem mit guter test-coverage (Testpyramide) entgegen gewirkt werden kann. 

Des Weiteren ist richtiges Zeitmanagement unumgänglich für das Projekt. Erreicht wird dies durch transparentes Projektmanagement und eine gute Informationspolititk untereinander.


## Auf Basis welcher Informationen sollen die Noten vergeben werden? Wann und in welcher Form werden diese zugänglich gemacht? (Jede/r Teilnehmer/in muss eine individuelle Note bekommen. Gruppennoten sind nicht erlaubt.)

Es ist geplant, die Benotungen in Form einer individualisierten Gruppennote zu gestalten. Die Gruppe soll zuerst als Ganzes bewertet werden, um die Zäsuren anschließend individuell an den Arbeitsumfang und die Komplexität der Aufgabenbereiche jedes Einzelnen anzupassen. Die Individualisierung soll mithilfe eines Meetings zwischen dem wissenschaftlichen Mitarbeiter und den Teilnehmern des Softwareprojekts erleichtert werden. Durch die von den Projektteilnehmern ausgearbeitete Dokumentation wird eine fundierte Bewertung der einzelnen Teilnehmer durch den zuständigen Professor und seine wissenschaftlichen Mitarbeiter gefördert.
