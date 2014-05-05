# Exposé

## Ausgangssituation im Projektumfeld, Projektziel (grob)

OParl ist ein offener Standard für parlamentarische Informationssysteme, der sich noch in Entwicklung befindet und voraussichtlich Anfang Juni verabschiedet wird. In einem parlamentarischen Informationssystem wird unter anderem gespeichert, welche Politiker den Ausschüssen angehören; zudem werden dort die Sitzungsprotokolle und die zugehörigen Drucksachen vorgehalten. Diese Informationen sind öffentlich, werden in der Regel aber nicht in einem maschinenlesbaren Format, sondern nur auf einer Webseite zur Verfügung gestellt. Mit OParl soll man diese Daten auch mit einer standardisierten JSON-API abfragen können.

Mit unserem Softwareprojekt wollen wir einen OParl-Validator bauen. Der Validator soll prüfen, ob ein Informationssystem den Standard richtig umgesetzt hat, ähnlich einem HTML-Validator. Er soll hauptsächlich Entwicklern von parlamentarischen Informationssystemen bei der Implementierung einer OParl-Schnittstelle helfen. Er soll weiterhin Nutzern der OParl-API ermöglichen, zu testen, ob die Daten in einem System noch valide sind. Die Entwicklung eines Validators war von den OParl-Entwicklern von vornherein vorgesehen. Wir wurden aus dem näheren Entwicklerumfeld gefragt, ob wir ihn im Rahmen eines Softwareprojekts realisieren wollen.

Der Validator soll als Konsolenanwendung und mit einem Web-Frontend benutzbar sein. Er soll einzelne Dokumente, einen Teil oder den ganzen Datensatz testen können. Er soll optional semantische Tests durchführen können, die über die Spezifikation hinaus gehen, aber Auskunft über Fehler in den Daten geben können. Weiterhin soll er eine Statistik über die validierten Daten ausgeben können, zum Beispiel welche optionalen, empfohlenen oder nicht spezifierten Angaben in welchem Umfang enthalten waren.

Neben der Entwicklung des Validators wollen wir im Rahmen des Softwareprojekts auch den bestehenden Referenzserver überarbeiten und während der Review-Phase den Standard auf Fehler überprüfen und gegebenfalls Feedback geben.


## Mitglieder des Projektteams; deren einschlägiges Vorwissen

Lucas, ist im achten Semester Bachelor Informatik. Hat gute
Kenntnisse in Webentwicklung und grundlegende Kenntnisse in Python
und Django.

Johannes ist im vierten Fachsemester des Bachelor Informatik und hat bereits gute Java-Kenntnisse und grundlegende Erfahrung mit Python, Haskell, Assemblersprache und C. 

Telofy (alias Denis Drescher) ist im zweiten Semester des Informatik-Masters,
benutzt seit fast zehn Jahren Python und hat seit 2010 als Backend-Entwickler
in drei Firmen gearbeitet, die Python einsetzen.

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
   Form haben, die es erlaubt sie zu deployen: die Validator-Library wird noch
   jegliche JSON-Objekte ablehnen, doch ihre Interfaces sollen bereits auf das
   Frontend-Projekt abgestimmt sein. Das Frontend-Projekt soll eine minimale
   Eingabemaske für JSON-Objekte zur Verfügung stellen und zur Validierung auf
   die Library zurückgreifen. Auf diese Seite können wir den Product Owners
   bereits Zugriff gewähren.
2. Ein existierender Server, der Testdaten ausliefert, soll erweitert worden
   sein, und der Validator soll bereits grundlegende Tests durchführen können. 
   Das Web-Frontend soll derweil benutzerfreundlicher sein, ins besondere im
   Bezug auf die Fehlerberichterstattung.
3. Gerade alle syntaktisch korrekten Objekte sollen akzeptiert werden, und das
   Frontend-Projekt soll auch JSONs über HTTP und HTTPS abrufen und validieren
   können.
4. Der Validator soll auch JSON-LD-Referenzen validieren, auch unter Beachtung
   von Weltwissen über die in den JSON-Objekten abgebildeten politischen Körper.
   Das Frontend-Projekt soll Hilfestellungen zur Lösung typischer Fehler leisten.
5. Um Hierarchien von Objekten vollständig und stichpunktartig validieren zu können,
   soll ein Crawler eine größere Anzahl von JSON-Objekten gezielt abrufen und in
   Bezugnahme aufeinander validieren können.


## Welche softwaretechnischen Methoden sollen wann wofür wie intensiv eingesetzt werden?

- Agil durch Kanban
- TDD
- Version control
- Mehr Stuff


## Welche anspruchsvollen Informatiktechniken sollen wofür eingesetzt werden?

- Django oder Flask
- Buildout


## Welches Mitglied hat welche Rolle oder Zuständigkeit?

- Kanban

Es gibt mehrere Rollen die werden immer wieder neu vergeben.


## Liste von Sprachen, Frameworks, Werkzeugen und Bausteinen, die voraussichtlich eingesetzt werden
    
- Python
- Django oder Flask
- Git
- Circus
- JSON/-LD
- Spline Pad
- GitHub


## Wie und wie oft wird der Kunde eingebunden?

Unsere Kunden sind die OParl-Entwickler. Da sie nicht aus Berlin kommen werden wir vorausichtlich voraussichtlich per E-Mail oder Telefon kommunizieren. Zum Beginn unseres Softwareprojekts wollen wir ihnen unseren Plan schicken und uns Feedback einholen. In den nächsten Wochen wird OParl in die Review-Phase kommen. Während dieser Zeit werden wir unser Feedback und verbleibende Fragen zur Spezifikation schicken. Anschließend werden wir die Entwickler vorausichtlich zu jedem Meilenstein über den aktuellen Stand informieren. Unsere Entwicklung wird auch auf GitHub verfolgbar sein.


## Welche Hauptrisiken bestehen für den Erfolg? Wie wird ihre Eintrittswahrscheinlichkeit reduziert oder die Wirkungen des Eintretens beherrscht?

Aufgrund der Tatsache, dass die zu validierende Norm noch nicht  fertiggestellt ist, wird das Hauptrisiko dieses Projekts sein, dass die  Spezifikation noch geändert werden könnte und der bereits ausgearbeitete  Teil der Software angepasst werden müsste. Um dieses Problem abzumildern, wollen wir bis Oparl die Version 1.0 erreicht, ausschließlich grundlegende Funktionen und Tests implementieren. Da die Tests unseres Validators für zukünftige OParl-Versionen leicht anpassbar sein sollen, werden unerwartete Änderungen zeitlich nicht zu schwer in Gewicht fallen.
Außerdem soll rege Kommunikation mit den Kunden dazu beitragen, dass wir auf dem aktuellen Stand sind und über zukünftige Änderung in der Spezifikation informiert werden.


## Auf Basis welcher Informationen sollen die Noten vergeben werden? Wann und in welcher Form werden diese zugänglich gemacht? (Jede/r Teilnehmer/in muss eine individuelle Note bekommen. Gruppennoten sind nicht erlaubt.)

Wir schlagen vor die  Benotungen in Form einer individualisierten Gruppennote zu gestalten.  Die Gruppe soll zuerst als Ganzes bewertet werden, um die Zensuren  anschließend individuell an den Arbeitsumfang und die Komplexität der  Aufgabenbereiche jedes Einzelnen anzupassen. Die Individualisierung soll  mit Hilfe eines Meetings zwischen den wissenschaftlichen Mitarbeitern und den Teilnehmern des Softwareprojekts erleichtert werden. Durch die, von den Projektteilnehmern ausgearbeitete Dokumentation, welche detailierte Informationen über die Arbeiten der einzelenen Projektteilnehmer enthält,  wird eine fundierte Bewertung der einzelnen Teilnehmer durch den  zuständigen Professor und seine wissenschaftlichen Mitarbeiter,  gefördert.
