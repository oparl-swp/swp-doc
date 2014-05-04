# Exposé

1. Ausgangssituation im Projektumfeld, Projektziel (grob)

    TODO

    (Bitte auch Frontend-Projekt und Library erwähnen, da ich später
    drauf Bezug nehme.)

2. Mitglieder des Projektteams; deren einschlägiges Vorwissen

    Lucas, ist im achten Semester Bachelor Informatik. Hat gute
    Kenntnisse in Webentwicklung und grundlegende Kenntnisse in Python
    und Django.

    Telofy (alias Denis Drescher) ist im zweiten Semester des Informatik-Masters,
    benutzt seit fast zehn Jahren Python und hat seit 2010 als Backend-Entwickler
    in drei Firmen gearbeitet, die Python einsetzen. Er hat mehr Erfahrung
    mit Python als mit anderen Programmiersprachen, findet aber auch Haskell
    ganz flauschig.

    - Universitärer Hintergrund
    - Beruflicher Hintergrund
    - Präferierte Programmiersprachen
    - Präferierte Libraries, Frameworks etc. im Bezug auf Python

3. Ungefährer Inhalt der Ergebnisse jeder Iteration; Zeitplan dazu
    
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

4. Welche softwaretechnischen Methoden sollen wann wofür wie intensiv
   eingesetzt werden?
    - Kanban
    - Mehr Stuff

5. Welche anspruchsvollen Informatiktechniken sollen wofür eingesetzt
   werden?
    - Django/Pyramid
    - Buildout

6. Welches Mitglied hat welche Rolle oder Zuständigkeit?
    - Kanban

    Es gibt mehrere Rollen die werden immer wieder neu vergeben.

7. Liste von Sprachen, Frameworks, Werkzeugen und Bausteinen, die
   voraussichtlich eingesetzt werden
    - Python
    - JSON / -LD
    - Spline Pad
    - Github

8. Wie und wie oft wird der Kunde eingebunden?
    - Vor Beginn des Projekts
    - noch mehr?
    - Bei Fertigstellung der Oparl Spezifikation

9. Welche Hauptrisiken bestehen für den Erfolg? Wie wird ihre
   Eintrittswahrscheinlichkeit reduziert oder die Wirkungen des
   Eintretens beherrscht?

   Aufgrund der Tatsache, dass die zu validierende Norm noch nicht fertiggestellt ist, wird das Hauptrisiko dieses Projekts sein, dass die Spezifikation noch geändert werden könnte und der bereits ausgearbeitete Teil der Software angepasst werden müsste. Dies würde sich negativ auf die Zeitplanung des Projekts auswirken. Um dieses Problem abzumildern, sollen deswegen, bis Oparl die Version 1.0 erreicht, ausschließlich grundlegende Funktionen und Tests implementiert werden.

    Außerdem soll der Validator, im Fall einer Änderung der Anforderungen, leicht anzupassen sein. Rege Kommunikation mit den Kunden soll dazu beitragen, dass beide Parteien immer auf dem aktuellen Stand der Dinge sind und um Fehler im Anforderungsmanagement schnell und effizient zu erkennen. 

    Ebenso wichtig ist, dass die Mitarbeiter untereinander ausreichend kommunizieren, um auf das Ausfallen von Mitarbeitern gut reagieren können. 

    Grundlegend ist mangelnde Robustheit, Benutzerfreundlichkeit und Performance ebenfalls ein nicht zu unterschätzendes Risiko, dem mit guter test-coverage (Testpyramide) entgegen gewirkt werden kann. 

    Des Weiteren ist richtiges Zeitmanagement unumgänglich für das Projekt. Erreicht wird dies durch transparentes Projektmanagement und eine gute Informationspolititk untereinander.

10. Auf Basis welcher Informationen sollen die Noten vergeben werden?
    Wann und in welcher Form werden diese zugänglich gemacht? (Jede/r
    Teilnehmer/in muss eine individuelle Note bekommen. Gruppennoten
    sind nicht erlaubt.)

    Es ist geplant, die Benotungen in Form einer individualisierten Gruppennote zu gestalten. Die Gruppe soll zuerst als Ganzes bewertet werden, um die Zäsuren anschließend individuell an den Arbeitsumfang und die Komplexität der Aufgabenbereiche jedes Einzelnen anzupassen. Die Individualisierung soll mithilfe eines Meetings zwischen dem wissenschaftlichen Mitarbeiter und den Teilnehmern des Softwareprojekts erleichtert werden. Durch die von den Projektteilnehmern ausgearbeitete Dokumentation wird eine fundierte Bewertung der einzelnen Teilnehmer durch den zuständigen Professor und seine wissenschaftlichen Mitarbeiter gefördert.