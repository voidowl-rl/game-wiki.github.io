---
#
---

# Dokumentation

Die Dokumentation eines Projekts ist ein an sich sehr simpler, aber extrem hilfreicher Arbeitsschritt. In ihm wird sichergestellt, dass eure Arbeitsergebnisse auch für alle anderen Teammitglieder verständlich sind, auch wenn sie nicht an der Erstellung des jeweiligen Codes beteiligt waren. Grundsätzlich geht es darum, dass der Code "sprechend" wird, also, dass ohne weitere Unterstützung deutlich wird, was der Code macht.

So ist zum Beispiel der folgenden Code nur schwer verständlich:

```kotlin
fun main() {
    abc()
}

fun abc() {
    var g = 0
    for (i in 1..100) {
        g = g + i
    }
    println(g)
}
```

In einem ersten Schritt kann der Code lesbarer und damit dokumentiert werden, indem sinnvolle Namen für Funktionen und Variablen (und Klassen) gewählt werden:
```kotlin
fun main() {
    summe1von100()
}

fun summe1von100() {
    var summe = 0
    for (aktuelleZahl in 1..100) {
        summe = summe + aktuelleZahl
    }
    println(summe)
}
```

In einem zweiten Schritt kann der Code durch Kommentare erweitert werden. Kommentare können beliebiger Text im Code sein und werden üblicherweise genutzt um den Code direkt darunter zu erläutern. Es gibt einzeilige Kommentare die mit dem Zeichen `//` initialisiert werden und mehrzeilige Kommentare die mit `/*` begonnen werden und mit `*/` abgeschlossen werden. Eine kommentierte und damit komplett dokumentierte Version des Codes könnte wie folgt aussehen:
```kotlin
fun main() {
    summe1von100()
}

/*
 * Die Funktion summe1von100 bildet die Summe der Zahlen von 1 bis 100
 * und gibt das Ergebnis auf der Konsole aus.
 */
fun summe1von100() {
    // Initialisiere die Summe mit 0
    var summe = 0
	
    // Laufe in einer Schleife durch die Zahlen von 1 bis 100
    for (aktuelleZahl in 1..100) {
        // Erhöhe die Summe um die jeweils verfügbare Zahl
        summe = summe + aktuelleZahl
    }
	
    // Gebe die Summe auf der Konsole aus
    println(summe)
}
```




