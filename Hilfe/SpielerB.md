---
#
---

# Der Spielerzug (Teil B)

Die Umsetzung solltet ihr, wie alle anderen Probleme in der Software-Entwicklung, schrittweise angehen, indem ihr die Schritte verwendet, die ihr zuvor gesammelt habt.

### Konsoleneingabe des Spielers auswerten

Wechselt hierzu in die Klasse `Spiel`. Überlegt, in welcher Funktion Spielereingaben ausgewertet werden sollten. Ergänzt anschließend die fehlenden und dokumentiert diese im Code.

### Überprüfen, ob die Bewegung möglich ist

Wie bei fast allen Problemen der Software-Entwicklung gibt es hier natürlich mehrere Ansätze. Überlegt zuerst, was ihr wissen müsst, bevor ihr entscheiden könnt, ob der Spieler sich in die Richtung bewegen kann, die er angegeben habt.

<details>
<summary>Selbstüberprüfung</summary>
1. Die Position des Spielers muss euch bekannt sein (z.B. durch spieler.x und spieler.y).
2. Die Zielposition des Spielers muss von euch berechnet worden sein (z.B. oben ist x = spieler.x und y = spieler.y - 1).
3. Eine Funktion in der Karte (o. ä.) muss aufgerufen werden, mit der ihr überprüfen könnt, ob ein Feld begehbar ist.
</details>

### Die Bewegung ausführen

An dieser Stelle müsst ihr die Koordinaten des Spielers auf die von euch überprüften aktualisieren.

### Eventuell: Die Münzen einsammeln

Überlegt zwischen welchen Objekten ihr die Positionen vergleichen müsst, um dies umzusetzen. Auf welche Attribute müsst ihr zugreifen und welche Funktionen müsst ihr unter Umständen aufrufen?

<details>
<summary>Selbstüberprüfung</summary>
Die Spielerposition muss mit denen jeder Goldmünze überprüft werden. 
Wenn der Spieler auf einer Goldmünze steht, die noch nicht eingesammelt wurde, muss die einsammeln-Funktion auf dieser aufgerufen werden.
Das Spielergold muss erhöht werden.
</details>

### Eventuell: Einen Gegner angreifen

Der Angriff funktioniert ähnlich zu dem Einsammeln von Münzen. Statt zu überprüfen, ob die Positionen identisch sind musst ihr stattdessen was überprüfen? Welche Funktion müsst ihr beim Spieler aufrufen, wenn ein Gegner neben ihm steht?

<details>
<summary>Selbstüberprüfung</summary>
Die Position über, unter, links und rechts neben dem Spieler muss mit den lebenden Gegnern abgeglichen werden.
Wenn ein Gegner auf diesen Positionen steht muss die greifeAn-Funktion ausgeführt werden.
</details>
<br>

<details markdown="1">
<summary>Welche Attribute benötigt der Spieler insgesamt?</summary>
1. Leben
2. Schaden
3. X-Position
4. Y-Position
5. IstTot
6. GesammelteMuenzen
</details>


