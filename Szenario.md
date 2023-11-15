--
#
--

# Szenariobeschreibung

Ihr seid ein Software-Entwickler-Team einer bekannten Spiele-Firma f�r Handy- und PC-Spiele. Der Donnerstag ist euch f�r die selbstst�ndige Weiterbildung �berlassen. Viele Kollegen nutzen diese Zeit, um sich �ber neue Technologien zu informieren oder eigene, der Firma n�tzliche, Projekte zu verfolgen. An diesem Donnerstag habt ihr als Team beschlossen, dass ihr die Zeit stattdessen gemeinsam nutzen wollt, um den Prototypen eines Spiels umzusetzen, der euch seit l�ngerer Zeit im Kopf vorschwebt. Ihr wollt diesen Prototypen nutzen, um eure Firma zu �berzeugen ein offizielles Produkt nach dem gleichen Spielprinzip zu entwickeln. Die grafische Darstellung und ausgefeilte Designs sind daher nicht so relevant, stattdessen muss lediglich die Hauptmechanik des Spiels ersichtlich werden. Das von euch geplante Spiel schlie�t an klassische Dungeon-Crawler an: Der Spieler befindet sich auf einer kleinen Karte, dem Dungeon und muss sich durch dieses bewegen und eine Reihe von Gegenst�nden einsammeln, um zu gewinnen. Dabei muss er Gegnern ausweichen oder diese besiegen � wird stattdessen er besiegt, ist das Spiel verloren. Ihr beschlie�t, dass euer Spiele-Prototyp f�r den Beginn nur aus einer Karte, zwei Gegnern, einem Spieler und der Sieg- bzw. Verlustbedingung bestehen soll. Ebenfalls soll auf eine grafische Ausgabe vorerst verzichtet werden, stattdessen soll einfach die Konsoleneingabe und -ausgabe genutzt werden.

Die Karte soll immer ein 20x8 gro�es Spielfeld darstellen. Intern soll sie durch einen String pro Zeiledargestellt werden. Die Karte soll verschiedene Elemente darstellen k�nnen:

- Das Zeichen # soll eine Wand darstellen, die unpassierbar ist.
- Das Zeichen ~ soll Wasser darstellen, welches unpassierbar ist.
- Das Zeichen . soll normalen, passierbaren Boden darstellen.

Die Karte soll als Koordinatensystem dienen, bei dem der Ursprung oben links liegt. Jedes Zeichen ist eine Spalte, jede Zeile eine Reihe.

Beide Gegner sollen eine feste Menge an Leben und Kampfkraft besitzen. Sie sind nicht passierbar. Sie sollen durch die Zeichen 1 und 2 dargestellt werden. Sie sollen sich auf der Karte bewegen k�nnen und dabei nur Felder betreten, die passierbar sind. Statt einer komplexen KI sollen die Gegner im Prototypen ein einfaches Verhalten haben: Wann immer sie am Zug sind sollen sie zuf�llig eine Richtung ausw�hlen und sich in diese bewegen, wenn es m�glich ist. Befinden sie sich nach der Bewegung neben dem Spieler sollen sie diesen angreifen bis entweder sie oder der Spieler tot sind. Stirbt ein Gegner soll er nicht mehr angezeigt werden.

Goldm�nzen sind Objekte, die durch das Zeichen o dargestellt werden. Sie sollen passierbar sein und k�nnen sich nicht bewegen. Entfernte Goldm�nzen sollen nicht mehr angezeigt werden.

Der Spieler soll ebenfalls eine feste Menge an Leben und Kampfkraft besitzen. Er ist nicht passierbar. Er soll durch das Zeichen X dargestellt werden. Durch die Konsoleneingaben hoch, runter, links, rechts soll der Spieler auf der Karte bewegt werden k�nnen, falls das Feld, auf das er bewegt werden soll, passierbar ist. Bewegt der Spieler sich auf eine Goldm�nze, soll diese entfernt werden und dem Gold des Spielers hinzugef�gt werden. Befindet sich der Spieler nach der Bewegung neben einem Gegner soll er diesen angreifen, bis entweder er oder der Gegner besiegt ist.

Das Spiel ist gewonnen, sobald alle Goldm�nzen eingesammelt worden sind.

Das Spiel ist verloren, sobald der Spieler besiegt ist.

Vor jedem Zug soll der aktuelle Zustand des Spiels auf der Konsole ausgegeben werden. Es muss daher die Karte in der richtigen Reihenfolge auf der Konsole angezeigt werden. Befindet sich auf einer Position ein Gegner, eine Goldm�nze oder der Spieler soll nicht das entsprechende Kartensymbol ausgegeben werden, sondern entsprechend Gegner/Spieler/Goldm�nze. Befindet sich auf der Position einer Goldm�nze ein Gegner oder der Spieler, soll nicht das Goldm�nzensymbol ausgegeben werden, sondern das Symbol des Gegners bzw. des Spielers. 

Damit die Symbole einfach auf der Konsole erkennbar sind beschlie�t ihr in eurem Programm eine Klasse �Stift� einzubinden, die ihr bereits zur Verf�gung stehen habt. Mit dieser seid ihr in der Lage die Ausgabe einzelner Zeichen auf der Konsole einzuf�rben.