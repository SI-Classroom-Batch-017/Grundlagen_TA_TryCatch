
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
Erstelle dazu einen Catch-Block mit dem Parameter “e: Exception”. Im Catch-Block soll jetzt mit der println()-Funktion der Text “Ein Fehler ist aufgetreten: “ ausgegeben werden.  
Darauffolgend soll auch der Fehler "e" über die println()-Funktion ausgegeben. Am Ende soll eine eigene Fehlermeldung “Dieses Produkt ist leider nicht mehr verfügbar.” über die println()-Funktion ausgegeben werden.

Das Programm soll also beim Ausführen den erzeugten Fehler richtig behandeln und den gewünschten Text ausgeben.

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

---
<details>
<summary><b>Aufgabe 7 - Code vorhersagen </b></summary>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

````
fun main() {ㅤ
    val sunnyDay: Boolean = true
    val rainy: Boolean = falseㅤ
    if (sunnyDay ) {ㅤㅤㅤㅤㅤㅤ
        if (!rainy) {ㅤ
            println("Heute fahre ich zum See")
        }ㅤ
    }else {ㅤ
        println("Heute bleibe ich zu Hause")
    }ㅤ
}ㅤ
ㅤ
````


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe7.kt*

</details>

---

<details>
<summary><b>Aufgabe 8 - Code vorhersagen </b></summary>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

````
fun main() {ㅤㅤ
    val uhrzeit: Int = 7ㅤㅤ
    val arbeitstag: Boolean = trueㅤㅤ
    val regen: Boolean = falseㅤㅤ
    if (uhrzeit>=6) {ㅤㅤ
        println("Der Wecker klingelt")ㅤㅤ
        if (!arbeitstag) {ㅤㅤ
            println("Ich bleibe einfach liegen")ㅤㅤ
        }else {ㅤㅤ
            println("Ich mache mich für den Tag bereit")ㅤㅤ
            if (regen) {ㅤㅤ
                println("Ich fahre mit dem Auto")ㅤㅤ
            }else {ㅤㅤ
                println("Heute nehme ich das Fahrrad")
            }ㅤㅤ
        }ㅤㅤ
    }ㅤㅤ
}
````


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe8.kt*

</details>

---


<details>
<summary><b>Aufgabe 9 - Code vorhersagen </b></summary>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

````
fun main() {ㅤㅤ
    val tiere: List<String> = listOf("Katze", "Giraffe", "Orca", "Bär" )ㅤㅤ
    when(tiere[2]) {ㅤㅤ
        "Katze" -> println("Löwe wird mit ${"Löwe".length} Buchstaben geschrieben")ㅤㅤ
        "Giraffe" -> println("Giraffe wird mit ${"Giraffe".length} Buchstaben geschrieben")ㅤㅤ
        "Orca" -> println("Orca wird mit ${"Orca".length} Buchstaben geschrieben")ㅤㅤ
        "Bär" -> println("Bär wird mit ${"Bär".length} Buchstaben geschrieben")ㅤㅤ

    }
}
````


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe9.kt*

</details>

---

<details>
<summary><b>Aufgabe 10 - Code vorhersagen </b></summary>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

````
fun main() {ㅤㅤ
    elementInListe("The Wire")ㅤㅤ
    elementInListe("Breaking Bad")ㅤㅤ
    elementInListe("The Office")ㅤㅤ
}

fun elementInListe(element: String) {ㅤㅤ
    val serien: List<String> = listOf("Game of Thrones", "How i Met your Mother", "Breaking Bad", "Stranger Things")ㅤㅤ
    val serieInListe = serien.contains(element)ㅤㅤ
    if(serieInListe) {ㅤㅤ
        println("Die Serie $element befindet sich in der Liste")
    }else{ㅤㅤ
        println("Die Serie $element befindet sich nicht in der Liste")
    }ㅤㅤ
}
````


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe10.kt*

</details>

---

<details>
<summary><b>Aufgabe 11 - Code vorhersagen </b></summary>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

````
fun main() {

    //Kunde 1
    val kunde1Name = "Bruce"ㅤㅤ
    val kunde1Preis = 346ㅤㅤ
    gutscheinBekommen(kunde1Preis, kunde1Name)
ㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤ
    //Kunde2ㅤㅤ
    val kunde2Name = "Tony"ㅤㅤ
    val kunde2Preis = 42ㅤㅤ
    gutscheinBekommen(kunde2Preis, kunde2Name)ㅤㅤ
    
    //Kunde3
    val kunde3Name = "Wanda"ㅤㅤ
    val kunde3Preis = 188ㅤㅤ
    gutscheinBekommen(kunde3Preis, kunde3Name)ㅤㅤ
    
}

fun gutscheinBekommen(preis: Int, name: String) {

    if (preis > 200) {ㅤㅤ
        println("$name bekommt einen Gutschein im Wert von 20€")
    }else if (preis > 100) {ㅤㅤ
        println("$name bekommt einen Gutschein im Wert von 10€")
    }else if (preis > 50) {ㅤㅤ
        println("$name bekommt einen Gutschein im Wert von 5€")
    }else{ㅤㅤ
        println("$name bekommt keinen Gutschein")
    }ㅤㅤ
}
````


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe11.kt*

</details>

---

<details>
<summary><b>Aufgabe 12 - Code vorhersagen </b></summary>

In dem gegebenen Code soll eine Ampelschaltung simuliert werden. Die Logik für die Schaltung liegt in der Funktion ampel(), die in der main()-Funktion nur aufgerufen wird. Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.


````
fun main () {ㅤㅤ
   var ampelPhase = "Grün"ㅤㅤ
    ampelPhase = ampel(ampelPhase)ㅤㅤ
    ampelPhase = ampel(ampelPhase)ㅤㅤ
    ampel(ampelPhase)ㅤㅤ


}

fun ampel(phase: String): String {ㅤㅤ
    var neuePhase: String = phase
    when(phase) {ㅤㅤ
        "Grün" -> {ㅤㅤ
            println("Die Ampel leuchtet grün, also dürfen die Autos jetzt fahren")ㅤㅤ
            neuePhase = "Gelb"ㅤㅤ
        }
        "Gelb" -> {ㅤㅤ
            println("Die Ampel leuchtet gelb, also müssen die Autos sich zum Anhalten bereit machen")
            neuePhase = "Rot"
        }
        "Rot" -> {
            println("Die Ampel leuchtet rot, also müssen die Autos warten")
            neuePhase = "Grün"
        }
    }ㅤㅤㅤㅤㅤㅤ
    return neuePhase
}
````


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe12.kt*

</details>

---

<details>
<summary><b>Aufgabe 13 Bonus - If-Else </b></summary>

Schreibe jetzt ein kleines Programm, dass ein simples Würfelspiel darstellen soll. Es sollen zwei Würfel geworfen werden und die Ergebnisse miteinander verglichen werden. Jeder Würfel gehört zu einem Spieler und je nachdem wer die höhere Zahl geworfen hat soll in der Konsole ein anderer Text ausgegeben werden:

- Spieler1 gewinnt: Spieler1 hat mit *Augenzahl* gegenüber Spieler2 mit *Augenzahl* gewonnen.
- Unentschieden: Beiden Spieler haben eine *Augenzahl* gewürfelt.
- Spieler2 gewinnt: Spieler2 hat mit *Augenzahl* gegenüber Spieler1 mit *Augenzahl* gewonnen.


**Datei für die Aufgabe:** *Grundlagen_TA_TryCatch → Aufgabe12.kt*

</details>
