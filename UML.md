---
#
---

# Unified Modelling Language

Euch ist bereits die Klassen- und die Objektkarte bekannt. Beides sind Elemente eines UML-Klassendiagramms. Ein UML-Klassendiagramm ist eine Sammlung von mehreren Klassenkarten. Der wichtigste Einsatzzweck des UML-Klassendiagramms ist es, alle Klassen, die für ein Projekt notwendig sind, auf einer Oberfläche planen zu können und miteinander in Verbindungen setzen zu können. Genau wie die Klassenkarte selbst ist es also vor allem ein Mittel zur Planung, welches vor der Umsetzung des Projekts als Code verwendet wird.

Das fertige UML-Klassendiagramm wird zudem oft in die Dokumentation des Projekts mit aufgenommen, denn es erlaubt einen Überblick über die Komponenten und die Struktur eines Projekts, ohne eine einzige Zeile Code lesen zu müssen.

Angenommen es gibt in einem Projekt nur zwei Klassen: Schüler und Deutschnote. Dann könnte ein dazu passendes UML-Klassendiagramm wie folgt aussehen:
![UML-Klassendiagramm ohne Beziehungen](/uml1.png)

Schüler und Deutschnote werden durch zwei Klassenkarte voneinander getrennt sinnvoll modelliert: der Schüler besitzt die Attribute zum Verwalten seines Vor- und Nachnames, des Geburtsdatums, der Klasse und des Jahrgangs. Die Attribute der Deutschnote hingegen bilden die einzelnen Teilnoten der Note ab. Des Weiteren verfügt die Klasse noch über eine Methode, um die Noten als Text auszugeben.

Doch welches Vorgehen muss gewählt werden, wenn um zu zeigen, dass jeder Schüler eine Deutschnote besitzt? Im Kotlin-Programmcode würde hierzu einfach eine weitere Variable angelegt werden die z.B. wie folgt aussehen würde: `var deutsch: Deutschnote`. 
Im Klassendiagramm ist es aber nicht sinnvoll, dem Schüler einfach ein zusätzliches Attribut zuzuweisen, welches `Deutschnote: Deutschnote` lautet, denn dann würde das Klassendiagramm seine Übersichtlichkeit verlieren: jede Klassenkarte müsste erst durchgelesen werden und dann müssten die dazu passenden Klassenkarten gesucht werden.
Stattdessen wird eine Pfeilverbindung wie im folgenden Bild angelegt:

![UML-Komposition](/uml2.png)

Die Pfeilverbindung stellt dar, dass ein Schüler immer eine Deutschnote besitzt. Die Art ihrer Beziehung kann über einen Text noch genauer spezifiziert werden (hier: "gehört zu"). Das Kriterium der Übersichtlichkeit wird gewahrt: auf einen Blick sind die Klassen und ihre Verbindungen ersichtlich. 
Die Pfeilspitze des Pfeils muss eine schwarze, ausgefüllte Raute sein. Sie zeigt immer auf die Klasse die aus anderen Klassen "zusammengesetzt" wird. Das Zusammensetzen einer Klasse aus (mehreren) anderen wird Komposition genannt.


