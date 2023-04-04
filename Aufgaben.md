
<h1 align="center">Grundlagen der Programmierung</h1>
<h3 align="center">Try-Catch</h3>
<br>


#### Beschreibung:

- Heute dreht sich alles um den try-catch Block, mit dem man Laufzeitfehler abfangen kann. Wenn du Funktionen benutzt, die in bestimmten Fällen einen Fehler erzeugen können, musst du die Verwendung dieser Methode in einen try Block packen. Der zugehörige catch Block fängt den Fehler, wenn nötig, auf und soll Code enthalten der sicherstellt, dass das Programm trotz des Fehlers richtig weiter läuft.


#### Hinweise zur Bearbeitung:

- Achte auf einen sauberen Quellcode, insbesondere Einrückungen sind wichtig!
- Wichtige Materialien für heute:
  - [Handbuch: Funktionen → Implementieren → try-catch implementieren](https://docs.google.com/document/d/13SyoQ3tgIr4T9tiUl42V5kiBGQwV4Lk-XA2SsKf-va0/edit#heading=h.rj9vymd1wa4z)


---

<details>
<summary> <b> Aufgabe 1 - Vorhersagen: Try-Catch mit Laufzeitfehler. </b> </summary>

In dieser Aufgabe bekommst du Code gegeben, in dem ein try-catch Block verwendet wird. Es geht dabei um die Buchung von Sitzplätzen in einem Flugzeug.

Schau dir den Codeausschnitt an.
- Was wird hier ausgegeben?

Notiere dir deine Antwort. (z.B. in einem Kommentar)  
Führe dann den Code aus.
- Wird das ausgegeben, was du dir notiert hast?

```
var availableSeats = 6

fun main() {
    try {
        reserveSeats(8)
    } catch (e: Exception) {
        println("Es sind leider nicht mehr genug Sitzplätze verfügbar.")
    }
}

fun reserveSeats(numberOfSeats: Int) {
    println("Es wird überprüft, ob noch " + numberOfSeats + " Sitzeplätze verfügbar sind...")
    if (numberOfSeats > availableSeats) {
        throw Exception("not enough available seats left")
    } else {
        availableSeats = availableSeats - numberOfSeats
        println("Die Sitzplätze wurden erfolgreich gebucht!")
    }
}
```

Hinweis: Eine Variable muss nicht zwingend innerhalb einer Funktion angelegt werden, 
sie kann auch außerhalb angelegt werden. 

**Modul für die Aufgabe:** *Aufgabe1*  
**Datei für die Aufgabe:** *1_TextAbgabe.kt*

</details>

---

<details>
<summary> <b> Aufgabe 2 - Vorhersagen: Try-Catch mit Laufzeitfehler. </b> </summary>



In dieser Aufgabe bekommst du Code gegeben, in dem ein try-catch Block verwendet wird.
Hier geht es um das Bestellen von Schuhen und was passiert, wenn keine Schuhe mehr da sind.

Schau dir den Codeausschnitt an.
- Was wird hier ausgegeben?

Notiere dir deine Antwort. (z.B. in einem Kommentar)  
Führe dann den Code aus.
- Wird das ausgegeben, was du dir notiert hast?

```
var numberOfShoes = 0

fun main() {
    try {
        orderShoes()
    } catch (e: Exception) {
        println("Diese Schuhe sind leider ausverkauft")
    }
}

fun orderShoes() {
    println("Es wird überprüft ob die Schuhe noch vorrätig sind...")
    if (numberOfShoes > 0) {
        println("Die Schuhe wurden bestellt")
        numberOfShoes = numberOfShoes - 1
    } else {
        throw Exception("no shoes available")
    }
}
```

**Modul für die Aufgabe:** *Aufgabe2*  
**Datei für die Aufgabe:** *2_TextAbgabe.kt*

</details>

---

<details>
<summary> <b> Aufgabe 3 - Try-Catch I</b> </summary>



In dieser Aufgabe ist eine Funktion mit dem Namen buyItem() gegeben, mit der ein Kunde ein Produkt kaufen kann. 
Diese erzeugt einen Fehler, falls das Produkt nicht mehr vorhanden ist.  
In diesem Beispiel erzeugt die Funktion immer einen Laufzeitfehler.   
In der main()-Funktion wird die Funktion buyItem() aufgerufen und es entsteht ein Laufzeitfehler.  

Deine Aufgabe ist es den erzeugten Laufzeitfehler aufzufangen, indem du den Funktionsaufruf buyItem() in einen Try-Block packst.  
Erstelle dazu noch einen Catch-Block mit dem Parameter “e: Exception”.  
Im Catch-Block soll jetzt mit der println()-Funktion der Text “Ein Fehler ist aufgetreten: “ ausgegeben werden.  
Dann wird auch der Fehler "e" über die println()-Funktion ausgegeben.
Am Ende wird noch eine eigene Fehlermeldung “Dieses Produkt ist leider nicht mehr verfügbar.” über die println()-Funktion ausgegeben.

Danach soll das Programm beim Ausführen den erzeugten Fehler richtig behandeln und den gewünschten Text ausgeben.

**Modul für die Aufgabe:** *Aufgabe3*  
**Datei für die Aufgabe:** *1_TryCatch.kt*

</details>

---

<details>
<summary> <b> Aufgabe 4 - Try-Catch II</b> </summary>

In dieser Aufgabe ist eine Liste "numbers" mit 4 Elementen vorgegeben. 
Darunter versuchen wir der Variable "number" das 10. Element aus der Liste zu geben.
Das geht nicht, da wir in der Liste nur 4 Elemente haben.
Das heißt, es wird ein Laufzeitfehler erzeugt.

Deine Aufgabe ist es nicht den Fehler zu beheben, sondern nur ihn aufzufangen. 
Schreibe einen Try-Catch-Block, der diesen Fehler auffängt. 
Dabei soll eine Fehlermeldung (denk dir eine Fehlermeldung aus) mit der println()-Funktion in der Konsole ausgegeben werden 
und der Wert der Variable “number” soll auf -1 gesetzt werden.

**Modul für die Aufgabe:** *Aufgabe4*  
**Datei für die Aufgabe:** *2_TryCatch.kt*

</details>

---
<details>
<summary> <b> Aufgabe 5 - Try-Catch III</b> </summary>

In dieser Aufgabe ist die Funktion divideByZero() mit einer Zahl "number" als Parameter gegeben.
Die Funktion teilt die Zahl durch 0. 
In der Mathematik können wir aber keine Zahl durch 0 teilen, deswegen erzeugt die Funktion 
einen Laufzeitfehler.

Deine Aufgabe ist es, die Funktion divideByZero() in der main()-Funktion aufzurufen 
und den erzeugten Laufzeitfehler mit einem Try-Catch-Block abzufangen.

**Modul für die Aufgabe:** *Aufgabe5*  
**Datei für die Aufgabe:** *3_TryCatch.kt*

</details>

---

<details>
<summary> <b> Aufgabe 6 - Try-Catch IV</b> </summary>

Wir wollen einen Türsteher simulieren, der unter 18-Jährige nicht in einen Club lässt.

Befolge dazu folgende Schritte:

1. Das Alter einer Person wird über die Konsole mit der readln()-Funktion eingelesen.  
Die Eingabe wird in der Variable alterInput gespeichert.
2. Dann wird ein Try-Catch-Block erstellt, indem wir die Eingabe versuchen 
zu einem Integer zu konvertieren. Hier kann ein Laufzeitfehler erzeugt werden.  
Schreibe dazu im Try-Block folgende Zeile: `var alter: Int = alterInput.toInt()`
3. Im Catch-Block geben wir eine geeignete Fehlermeldung aus, wenn ein Laufzeitfehler entsteht.
4. Im Try-Block geben wir: "Willkommen, hier ist dein Bier, let's party!" in der Konsole aus,
wenn das Alter größer oder gleich 18 ist.   
Ansonsten geben wir: "Sorry, kein Einlass zur Party. Ist ab 18." in der Konsole aus.


Probier dann dein Programm aus.   
Lass es ein paar mal laufen und gib dann über die
Konsole verschiedene Alter ein.  
Macht der Türsteher seinen Job?  
Was passiert, wenn du keine Zahl, sondern einen Text in der Konsole eingibst?

**Modul für die Aufgabe:** *Aufgabe6*  
**Datei für die Aufgabe:** *4_TryCatch.kt*


</details>



