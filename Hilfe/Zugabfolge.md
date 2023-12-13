---
#
---

# Die Zugabfolge

Die Züge im Spiel sollen nach einem festen Schema passieren. Eine Möglichkeit ist es, erst den Spieler spielen zu lassen, dann die Gegner und dann alle Sieg- oder Verlust-Bedingungen zu überprüfen. Detaillierte könnte dies so aussehen:

1. Karte ausgeben.
2. Spielereingabe annehmen .
3. Bewegung auf Basis der Spielereingabe machen.
4. Wenn möglich: Münze einsammeln.
5. Wenn möglich: Gegner angreifen.
6. Gegner1 bewegen (wenn lebendig).
7. Wenn möglich: Spieler angreifen.
8. Gegner2 bewegen (wenn lebendig).
9. Wenn möglich: Spieler angreifen.
10. Wenn Spieler drei Münzen hat: Spiel mit Siegesmeldung beenden.
11. Wenn Spieler 0 Leben hat: Spiel mit Verlustmeldung beenden.
12. Sonst: Zug beenden und nächsten starten.