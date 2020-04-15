<!--

author:   Sebastian Zug & Georg Jaeger
email:    sebastian.zug@informatik.tu-freiberg.de & georg.jaeger@informatik.tu-freiberg.de
version:  1.0.0
language: de
narrator: Deutsch Female

comment:  This is a very simple comment.
          Multiline is also okay.

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
          https://felixhao28.github.io/JSCPP/dist/JSCPP.es5.min.js

link: https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css

translation: Deutsch  translations/German.md
translation: Français translations/French.md
translation: Русский  translations/Russian.md


-->

# Praktische Phase des Softwaretechnologie-Projektes 2020

Die interaktive Ansicht dieses Kurses ist unter folgendem [Link](https://liascript.github.io/course/?https://raw.githubusercontent.com/TUBergakademieFreiberg/Softwaretechnologieprojekt2020/master/README.md) verfügbar.

## Aufgabenkomplexe

**1. Extraktion von RoboCup Objekten aus 2D Kamera-Bildern**

   In diesem Kontext arbeiten die Teams kompetitiv an einer identischen
   Aufgabenstellung. Wir haben einen Zugriff auf mehrere tausend Bilder anderer
   Teams, die den Blick des Roboters auf die Arbeitsflächen enthalten. Darauf sind
   die zu handhabenden Objekte mehr oder minder wahllos verstreut. Diese müssen
   erkannt und im Bildkoordinatensystem lokalisiert werden.

**2. Spezifische Module für ERIKA**

   In diesem Komplex zielen die Aufgaben auf die weitere Entwicklung der Fertigkeiten
   von ERIKA, unserem RoboCup@Work-System. Hier stehen die folgenden Themen zur Auswahl:

* **Statemachine** - Überwachung und Darstellung des Zustands in dem sich der Roboter befindet
* **Wahrnehmung** - Sensorische Wahrnehmung des Roboter und entsprechende Verarbeitung (z.B. Filter)
* **Navigation** - Planung und Ausführung von Bewegungen des Roboters basierend auf den Daten des aktuellen Weltmodells
* **Manipulator** - Greifen von detektierten Objekten (siehe Aufgabenkomplex 1)

### Extraktion von RoboCup Objekten aus 2D Kamera-Bildern

Zur Extraktion wird ein allgemeines Vorgehen der entsprechenden Abbildung angenommen:

<!-- style="display: block; margin-left: auto; margin-right: auto; max-width: 315px;" -->
```    ascii
  +-------------+   +------------+   +---------------+   +-------------+
  |             |   |            |   |               |   |             |
  |   Dateien   +-->| Datenbank  +-->+ Klassifikator +-->|  Ergebnis   |
  |    (.jpg)   |   | (optional) |   |               |   | (.jpg/.xml) |  
  |             |   |            |   |               |   |             |
  +-------------+   +------------+   +---------------+   +-------------+
```

* Eingabe: Pfad zu einem Ordner mit Bild-Dateien (.jpg)
* Ausgabe: Pfad zu einem Ordner, der mit Klassifikationsergebnissen (.xml) und Bild-Dateien gefüllt wird (.jpg).

Der Klassifikator durchläuft dabei im allgemeinen folgende Schritte:

1. Lesen/Empfangen eines Bildes
2. Durchsuchen der Pixel zur Detektion von Mustern
   * Wenn Muster erkannt: Objekt ist detektiert, Bounding Box wird gebildet
3. Klassifikation der detektierten Objekte (möglicherweise zuammen mit Schritt 2)
4. Ausgabe der Liste der detektierten Objekte mit Bounding Box und Namen als XML-Datei

**Daten**

Die Daten, die euch zur Verfügung stehen, setzen sich aus einem Trainingsdatenset und Validierungsdaten zusammen. Zur Bestimmung der Güte eurer Klassifikatoren, werden wir ein separates Set von Testdaten bereithalten.

**Aufruf**

Um euren Klassifikator mit den Testdaten testen zu können, soll folgender Aufruf genügen:

```
./classifier --input <path-to-folder-containig-images> --output <path-to-output-folder>
```

**Zielsystem**

Das Zielsystem ist ein Ubuntu 18.04.

**Test-Skript**

Wir werden im Laufe des Semesters ein Programm zum Testen eurer Klassifikatoren veröffentlichen. Diese Programm wird auch für den finalen Test genutzt. Ihr könnt es bereits während des Semester nutzen um die Performance eurer Klassifikatoren einzuschätzen.

### Spezifische Module für ERIKA

* **Statemachine** - Überwachung und Darstellung des Zustands in dem sich der Roboter befindet
* **Wahrnehmung** - Sensorische Wahrnehmung des Roboter und entsprechende Verarbeitung (z.B. Filter)
* **Navigation** - Planung und Ausführung von Bewegungen des Roboters basierend auf den Daten des aktuellen Weltmodells
* **Manipulator** - Greifen von detektierten Objekten (siehe Aufgabenkomplex 1)

## Ablaufplan

Wöchentliche Meetings:
* Gruppen zum ersten Aufgabenkomplexe Montags 09:15 - 10:45
* Gruppen zum zweiten Aufgabenkomplexe Montags 16:00 - 17:30

Zusätzlich werden an diesen Terminen die Vorträge eingegliedert:

**Ablaufplan für die Vorträge**

| **Datum**              | **Vorträge**     |
|:-----------------------|:-----------------|
| 04.05.20 09:15 - 10:45 | Exposé           |
| 04.05.20 16:00 - 17:30 | Exposé           |
| 11.05.20 09:15 - 10:45 | Exposé           |
| 11.05.20 16:00 - 17:30 | Exposé           |
| 08.06.20 09:15 - 10:45 | Zwischenstand    |
| 08.06.20 16:00 - 17:30 | Zwischenstand    |
| 15.06.20 09:15 - 10:45 | Zwischenstand    |
| 15.06.20 16:00 - 17:30 | Zwischenstand    |
| 13.07.20 09:15 - 10:45 | Abschlussvortrag |
| 13.07.20 16:00 - 17:30 | Abschlussvortrag |
| 20.07.20 09:15 - 10:45 | Abschlussvortrag |
| 20.07.20 16:00 - 17:30 | Abschlussvortrag |

## Bewertungskriterien und ihre Gewichtung

**1. Vorträge (2/3)**

Die Exposé-, Zwischenstands- und Verteidigungsvorträge werden mit 2/3 den Großteil der Bewertung ausmachen.
Hier geht es darum alle Aspekte des Projektes anschaulich und selbstkritisch Darzustellen.

**2. Dokumentation (1/9)**

Ebenfalls von großer Bedeutung bei Softwareprojekten ist die hinreichende Dokumentation der Software.
Dementsprechend fließt auch diese in die Bewertung mit ein.
Entscheidend ist hierbei jedoch, dass (neben den Vorträgen, die auch der Dokumentation dienen) eine Anleitung zur Nutzung der Software sowie für mögliche Weiterentwicklungen entsteht.

**3. Tooling (1/9)**

Neben den dokumentativen Aufgaben kann der Einsatz der richtigen Tools dramatisch zum Erfolg/Misserfolg eines Projektes beitragen.
Dementsprechend (soweit sinnvoll) Tools zur Automatisierung/Unterstützung des Entwicklungsprozesses eingesetzt werden.
Dokumentiert sowohl den Einsatz der Tools, als auch, wie hilfreich ihr diese Empfunden habt.

**4. Softwarearchitektur (1/9)**

Letztlich steht auch die Softwarearchitektur als zentrale Komponent eines Softwareprojekts im Fokus des Semesters.
Hier soll vor allem eine konsistente, intuitive Struktur angestrebt werden.


**Beispielrechnung:**

| **Vortrag 1**   | **Vortrag 2**    | **Vortrag 3**    | **Dokumentation** | **Tooling**      | **Softwarearchitektur** | **Note** |
|:----------------|:-----------------|:-----------------|:------------------|:-----------------|:------------------------|:---------|
| $1.0 \cdot 2/9$ | $2.3 \cdot  2/9$ | $1.3 \cdot  2/9$ | $2.0 \cdot 1/9$   | $1.3 \cdot  1/9$ | $1.7 \cdot 1/9$         | **1.7**  |
