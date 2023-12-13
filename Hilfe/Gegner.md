---
#
---

# Der Gegnerzug

Der Zug des Gegners läuft fast identisch zu dem des Spielers ab, er besteht lediglich aus weniger Schritten.

### Bewegungsrichtung auswählen

Statt eine Eingabe zu verwenden, erstellt ihr eine Zufallszahl zwischen 0, 1, 2, 3. Bei 0 bewegt sich der Gegner nach oben, bei 1 nach unten usw. Wenn der Gegner sich nicht in die jeweilige Richtung bewegen kann, ignoriert ihr dies einfach und der Gegner macht in diesem Zug nichts. Die Überprüfung, ob die Bewegung möglich ist, ist dieselbe wie beim Spieler. Um die Bewegung auszuführen aktualisiert die x- und y-Koordinate des Gegnerobjekts.

### Eventuell: Den Spieler angreifen

Dies funktioniert äquivalent wie beim Spieler: ist der Spieler links neben, rechts neben, unter oder über dem Gegner, greift der Gegner diesem mit seinem Schadenswert an. Fallen die Lebenspunkte des Spielers unter 0 ist dieser "tot".

<details markdown="1">
<summary>Welche Attribute benötigt der Gegner insgesamt?</summary>
1. Leben
2. Schaden
3. X-Position
4. Y-Position
5. IstTot
</details>
