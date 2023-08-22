<h1 align="center">Grundlagen der Programmierung</h1>
<h2 align="center">Try-Catch</h2>
<br>

### Beschreibung:
Der try-catch Block wird benutzt, um Laufzeitfehler abzufangen.  
Wenn du Funktionen benutzt, die in bestimmten Fällen einen Fehler erzeugen können, 
musst du die Verwendung dieser Funktion in einen try Block packen. 
Der zugehörige catch Block fängt den Fehler, welcher auftreten könnte auf 
und soll Code enthalten der sicherstellt, 
dass das Programm trotz des Fehlers richtig weiter läuft.


### Hinweise zur Bearbeitung:
- Lies erst die ganze Aufgabenstellung, bevor du die Aufgabe bearbeitest.
- Achte auf einen sauberen Quellcode, insbesondere Einrückungen sind wichtig!
- Nutze den Debugger, wenn du nicht mehr weiter weißt.
- Achte darauf deinen Code sinnvoll zu kommentieren.

---
### Aufgabe 1 - Vorhersagen: Try-Catch mit Laufzeitfehler I

<details>

In dieser Aufgabe bekommst du Code gegeben, in dem ein try-catch Block verwendet wird.  
Es geht dabei um die Buchung von Sitzplätzen in einem Flugzeug.

Schau dir den Codeausschnitt an.
- Was wird hier ausgegeben?

Notiere dir deine Antwort. (z.B. in einem Kommentar)  
Führe dann den Code aus.
- Wird das ausgegeben, was du dir notiert hast?

```kotlin
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

> Hinweis: Eine Variable muss nicht zwingend innerhalb einer Funktion angelegt werden, 
sie kann auch außerhalb angelegt werden. 

**Modul für die Aufgabe:** *Aufgabe1*  
**Datei für die Aufgabe:** *1_TextAbgabe.kt*

</details>

---
### Aufgabe 2 - Vorhersagen: Try-Catch mit Laufzeitfehler II

<details>

In dieser Aufgabe bekommst du Code gegeben, in dem ein try-catch Block verwendet wird.  
Hier geht es um das Bestellen von Schuhen und was passiert, wenn keine Schuhe mehr da sind.

Schau dir den Codeausschnitt an.
- Was wird hier ausgegeben?

Notiere dir deine Antwort. (z.B. in einem Kommentar)  
Führe dann den Code aus.
- Wird das ausgegeben, was du dir notiert hast?

```kotlin
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

### Aufgabe 3 - Try-Catch I

<details>

In dieser Aufgabe ist eine Funktion `buyItem()` gegeben, mit der ein Kunde ein Produkt kaufen kann.  
Diese erzeugt einen Fehler, falls das Produkt nicht mehr vorhanden ist.  
In diesem Beispiel erzeugt die Funktion immer einen Laufzeitfehler.

Deine Aufgabe ist es den erzeugten Laufzeitfehler aufzufangen, indem du den Funktionsaufruf `buyItem()` in der `main()` in einen Try-Block packst.  
Erstelle dazu einen Catch-Block mit dem Parameter `e: Exception`.
Im Catch-Block soll jetzt mit der println()-Funktion der Text `Ein Fehler ist aufgetreten: ` zusammen mit der Exception `e` ausgegeben werden.  
Am Ende sollte auf der Konsole also stehen:

```
Ein Fehler ist aufgetreten: item not in stock exception
```

**Modul für die Aufgabe:** *Aufgabe3*  
**Datei für die Aufgabe:** *1_TryCatch.kt*

</details>

---

### Aufgabe 4 - Try-Catch II

<details>

In dieser Aufgabe ist eine Liste `numbers` mit 4 Elementen vorgegeben.  
Darunter versuchen wir der Variable `number` das 10. Element aus der Liste zu geben.
Das geht nicht, da wir in der Liste nur 4 Elemente haben.
Das heißt, es wird ein Laufzeitfehler erzeugt.

Deine Aufgabe ist es nicht den Fehler zu beheben, sondern nur ihn aufzufangen. 
Schreibe einen Try-Catch-Block, der diesen Fehler auffängt. 
Dabei soll eine Fehlermeldung (denk dir eine Fehlermeldung aus) mit der println()-Funktion in der Konsole ausgegeben werden 
und der Wert der Variable `number` soll auf `-1` gesetzt werden.

**Modul für die Aufgabe:** *Aufgabe4*  
**Datei für die Aufgabe:** *2_TryCatch.kt*

</details>

---

### Aufgabe 5 - Try-Catch III

<details>

In dieser Aufgabe ist die Funktion `divideByZero(number: Int)` gegeben.
Die Funktion teilt die gegebene Zahl durch 0. 
In der Mathematik können wir aber keine Zahl durch 0 teilen, deswegen erzeugt die Funktion 
einen Laufzeitfehler.

Deine Aufgabe ist es, die Funktion `divideByZero()` aufzurufen 
und den erzeugten Laufzeitfehler mit einem Try-Catch-Block abzufangen.

**Modul für die Aufgabe:** *Aufgabe5*  
**Datei für die Aufgabe:** *3_TryCatch.kt*

</details>

---

### Aufgabe 6 - Try-Catch IV

<details>

Wir wollen einen Türsteher simulieren, der Personen unter 18 nicht in einen Club lässt.

Befolge dazu folgende Schritte:

1. Das Alter einer Person wird über die Konsole mit readln() eingelesen.
2. Dann wird ein Try-Catch-Block erstellt, indem wir die Eingabe versuchen 
zu einem Integer zu konvertieren. Hier kann ein Laufzeitfehler erzeugt werden.
3. Im Catch-Block geben wir eine geeignete Fehlermeldung aus, wenn ein Laufzeitfehler entsteht.
4. Im Try-Block geben wir: `Willkommen, hier ist dein Bier, let's party!` in der Konsole aus,
wenn das Alter größer oder gleich 18 ist.  
Ansonsten geben wir: `Sorry, kein Einlass zur Party. Ist ab 18.` in der Konsole aus.


Probier dann dein Programm aus.  
Lass es ein paar Mal laufen und gib dann über die
Konsole verschiedene Alter ein.  
Macht der Türsteher seinen Job?  
Was passiert, wenn du keine Zahl, sondern Buchstaben in der Konsole eingibst?

**Modul für die Aufgabe:** *Aufgabe6*  
**Datei für die Aufgabe:** *4_TryCatch.kt*


</details>

---

### Aufgabe 7 - Code vorhersagen I

<details>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

````
fun main() {ㅤ
    val sunnyDay: Boolean = true
    val rainy: Boolean = falseㅤ
    if (sunnyDay) {ㅤㅤㅤㅤㅤㅤ
        if (!rainy) {ㅤ
            println("Heute fahre ich zum See")
        }ㅤ
    }else {ㅤ
        println("Heute bleibe ich zu Hause")
    }ㅤ
}ㅤ
ㅤ
````

**Modul für die Aufgabe:** *Aufgabe7-12*  
**Datei für die Aufgabe:** *Aufgabe7.kt*

</details>

---

### Aufgabe 8 - Code vorhersagen II

<details>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

```kotlin
fun main() {ㅤㅤ
    val uhrzeit: Int = 7ㅤㅤ
    val arbeitstag: Boolean = trueㅤㅤ
    val regen: Boolean = falseㅤㅤ
    if (uhrzeit>=6) {ㅤㅤ
        println("Der Wecker klingelt")ㅤㅤ
        if (!arbeitstag) {ㅤㅤ
            println("Ich bleibe einfach liegen")ㅤㅤ
        } else {ㅤㅤ
            println("Ich mache mich für den Tag bereit")ㅤㅤ
            if (regen) {ㅤㅤ
                println("Ich fahre mit dem Auto")ㅤㅤ
            }else {ㅤㅤ
                println("Heute nehme ich das Fahrrad")
            }ㅤㅤ
        }ㅤㅤ
    }ㅤㅤ
}
```

**Modul für die Aufgabe:** *Aufgabe7-12*  
**Datei für die Aufgabe:** *Aufgabe8.kt*

</details>

---

### Aufgabe 9 - Code vorhersagen III

<details>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

```kotlin
fun main() {ㅤㅤ
    val tiere: List<String> = listOf("Katze", "Giraffe", "Orca", "Bär" )ㅤㅤ
    when(tiere[2]) {ㅤㅤ
        "Katze" -> println("Löwe wird mit ${"Löwe".length} Buchstaben geschrieben")ㅤㅤ
        "Giraffe" -> println("Giraffe wird mit ${"Giraffe".length} Buchstaben geschrieben")ㅤㅤ
        "Orca" -> println("Orca wird mit ${"Orca".length} Buchstaben geschrieben")ㅤㅤ
        "Bär" -> println("Bär wird mit ${"Bär".length} Buchstaben geschrieben")ㅤㅤ
    }
}
```

**Modul für die Aufgabe:** *Aufgabe7-12*  
**Datei für die Aufgabe:** *Aufgabe9.kt*

</details>

---

### Aufgabe 10 - Code vorhersagen IV

<details>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

```kotlin
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
```

**Modul für die Aufgabe:** *Aufgabe7-12*  
**Datei für die Aufgabe:** *Aufgabe10.kt*

</details>

---

### Aufgabe 11 - Code vorhersagen V

<details>

Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.

```kotlin
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
    } else if (preis > 100) {ㅤㅤ
        println("$name bekommt einen Gutschein im Wert von 10€")
    } else if (preis > 50) {ㅤㅤ
        println("$name bekommt einen Gutschein im Wert von 5€")
    } else{ㅤㅤ
        println("$name bekommt keinen Gutschein")
    }ㅤㅤ
}
```

**Modul für die Aufgabe:** *Aufgabe7-12*  
**Datei für die Aufgabe:** *Aufgabe11.kt*

</details>

---

### Aufgabe 12 - Code vorhersagen VI

<details>

In dem gegebenen Code soll eine Ampelschaltung simuliert werden. Die Logik für die Schaltung liegt in der Funktion ampel(), die in der main()-Funktion nur aufgerufen wird. Guckt euch den gegebenen Code an und beschreibt was in der Konsole ausgegeben wird.


```kotlin
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
```

**Modul für die Aufgabe:** *Aufgabe7-12*  
**Datei für die Aufgabe:** *Aufgabe12.kt*

</details>

---

### Aufgabe 13 - _Bonus_ If-Else

<details>

Schreibe jetzt ein kleines Programm, dass ein simples Würfelspiel darstellen soll. Es sollen zwei Würfel geworfen werden und die Ergebnisse miteinander verglichen werden. Jeder Würfel gehört zu einem Spieler und je nachdem wer die höhere Zahl geworfen hat soll in der Konsole ein anderer Text ausgegeben werden:

- Spieler1 gewinnt: Spieler1 hat mit *Augenzahl* gegenüber Spieler2 mit *Augenzahl* gewonnen.
- Unentschieden: Beiden Spieler haben eine *Augenzahl* gewürfelt.
- Spieler2 gewinnt: Spieler2 hat mit *Augenzahl* gegenüber Spieler1 mit *Augenzahl* gewonnen.


**Modul für die Aufgabe:** *Aufgabe13*  
**Datei für die Aufgabe:** *Aufgabe13.kt*

</details>

