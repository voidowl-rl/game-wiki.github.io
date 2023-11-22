---
#
---

# Die Karte einlesen und ausgeben

Die Beispielkarte, die du im Starterprojekt einsehen kannst ist die Folgende:
```
####################
#....~.............#
#....~....1....o...#
#...o~..2......o...#
#..~~~~~~..........#
#...........X......#
#################### 
```

Es ist zu Veranschaulichung sinnvoll sich die Karte in einem Koordinatensystem erfasst vorzustellen:

y\\x |0|1|2|3|4|5|6|7|8|9|...
---|-|-|-|-|-|-|-|-|-|-|---
0  |\#|\#|\#|\#|\#|\#|\#|\#|\#|\#|...
1  |\#|.|.|.|.|~|.|.|.|.|...
2  |\#|.|.|.|.|~|.|.|.|1|...
3  |\#|.|.|.|o|~|.|.|2|.|...
4  |\#|.|.|~|~|~|~|~|~|.|...
5  |\#|.|.|.|.|.|.|.|.|.|...
6  |\#|\#|\#|\#|\#|\#|\#|\#|\#|\#|...

Dadurch kann jedes Zeichen der Welt einer Koordinate zugeordnet werden. Zeitgleich kann dieses Koordinatensystem als Grundlage genutzt werden, um die Position der weiteren Spielelemente (Spieler, Gegner, Münzen) zu speichern.

Trotzdem ist der String im Code natürlich nur eine einzelne, lange Zeichenkette. Sie ist also *eindimensional*, denn die für uns angezeigten Zeilenumbrüche sind für das Programm nur beliebige weitere Zeichen. In einem String können sie durch den Code `\n` dargestellt werden.

Der Anfang unserer Beispielkarte sieht also in Wirklichkeit für das Programm so aus:
`####################\n#....~.............#\n`

In deinem Team solltest du erst einmal zwei Fragen lösen:

1) Wie speichere ich die Rohdaten (die Zeilen) in meiner Welt-Klasse ab?

2) Wie gebe ich die Karte aus?


<details markdown="1">
<summary>Hinweise zu Frage 1</summary>

Die einfachste Möglichkeit, diese in der Welt-Klasse zu speichern, ist es die im constructor verfügbare Variable `alleZeilen` in einer Klassenvariable abzuspeichern. Die Klassenvariablen zeile1 bis zeile7 könnt ihr hingegen aus dem Starterprojekt entfernen.<br><br>

Doch halt! Einfach so könnt ihr die Variable nicht speichern - in der Variable `alleZeilen` sind Münzen, Gegner und Spieler enthalten - Elemente des Spiels die sich unter Umständen bewegen oder verschwinden.<br><br>

Sinnvoll ist es stattdessen die vorhandene Schleife zu benutzen:<br><br>

```kotlin
var weltDaten = ""

for (position in 0 .. alleZeilen.length - 1) {
	var aktuellesZeichen: Char = alleZeilen[position]
	
	if (aktuellesZeichen == 'o') {
		// Erstelle an dieser Stelle ein neues Objekt der Klasse Münze
		// TODO
		
		// Und setze auf der Karte einen .
		weltDaten = weltDaten + '.'
	} else if (aktuellesZeichen == '1' || aktuellesZeichen == '2' ) {
		// Analog der Code für die Behandlung der Gegner
	} else if (aktuellesZeichen == 'X') {
		// Analog der Code für die Behandlung des Spielers
	} else {
		// Wenn kein besonderes Zeichen da ist, übernehme es
		weltDaten = weltDaten + aktuellesZeichen
	}
}
```

Nach Durchlauf der Schleife habt ihr dann eine Variable `weltDaten`, die nur die Welt, nicht aber die dynamischen Elemente darin beinhaltet. Diese könnt ihr in einer Klassenvariable speichern.
</details>
 


<details>
<summary>Hinweise zu Frage 2</summary>

Zur Ausgabe müsst ihr die Funktion zeichneWelt befüllen. Dazu gebt ihr einfach der Reihe nach mit der Klasse Stift (wenn ihr Farbe möchtet) oder der print-Methode die einzelnen Zeichen nacheinander aus.<br><br>
Bevor ihr das einzelne Zeichen ausgebt solltet ihr prüfen, ob an der Position des Zeichens gerade ein Spieler, eine Münze (die nicht aufgehoben wurde) oder ein Gegner (der noch lebt) steht. Ist dies der Fall, gebt stattdessen das Zeichen für das jeweilige Objekt aus!<br>
</details>
 

### Eindimensionale Strings, zweidimensionalene Welt
Es gibt natürlich ein kleines Problem: Da eure Daten in einem einzelnen String gespeichert sind, habt ihr innerhalb dieses String gar nicht eure zweidimensionalen Positionen, die zur Verwaltung der Bewegungen und der Objekt-Positionen sehr sinnvoll wären. Stattdessen habt ihr nur einen eindimensionalen Wert, wie zum Beispiel in dieser Schleife hier:
`for (position in 0..alleZeilen.length - 1)`

Zum Glück ist dies kein Problem, da eure Karte eine feste Größe hat. Das bedeutet, ihr könnt aus zweidimensionalen Koordinaten eine Position im String berechnen und andersrum:

X und Y zu String-Position:
```kotlin
var position = y * 21 + x
```

Erläuterung: In jeder "Zeile" sind 21 Zeichen: die 20 der Karte und am Zeilenende das Zeichen für den Zeilenumbruch. Die Position des ersten Zeichens der zweiten Zeile ist daher 21 (da wir in der Informatik immer mit 0 anfangen zu zählen). Um nun an die richtige x-Position des Koordinatensystems zu kommen wird einfach der x-Wert addiert (der ebenfalls bei 0 startet, siehe obiges Koordinatensystem).

String-Position zu X und Y:
```kotlin
var x = position % 21
var y = position / 21
```

Erläuterung: Wir kehren die obige Rechnung einfach um. Der y-Wert ist das Ergebnis einer *ganzzahligen* Division durch 21. Bei einer ganzzahligen Division ist das Ergebnis stets nur die Ganzzahl, keine Komma-Zahl. Der x-Wert ist der *Rest* einer *ganzzahligen* Division. Dieser Rest kann durch den sogenannten modulo-Operator erfasst werden, der in Kotlin das %-Zeichen ist. Es handelt sich um einen normalen mathematischen Operator wie +, -, * oder /.

Es ist sinnvoll, die beiden Rechnungen in Funktionen umzuwandeln, sodass ihr sie nur einmal schreiben müsst.