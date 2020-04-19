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



-->

# Praktische Phase des Softwaretechnologie-Projektes 2020

Die interaktive Ansicht dieses Kurses ist unter folgendem [Link](https://liascript.github.io/course/?https://raw.githubusercontent.com/TUBergakademieFreiberg/Softwaretechnologieprojekt2020/master/README.md) verfügbar.

Das Ziel des Softwaretechnologie-Projektes ist die Vermittlung praktischer Fähigkeiten und Vorgehensweise zur Erstellung von Software in einem Teamprojekt.

In diesem Jahr stehen dazu zwei Aufgabenkomplexe zur Auswahl:

1. Extraktion von RoboCup-Objekten aus 2D Kamera-Bildern
2. Spezifische Module für ERIKA

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

**Gegeben:** Trainings- und Validierungsdaten bestehend aus Bildern (.jpg) und Metadaten (.xml). Die Metadaten umfassen im wesentlichen die Namen/Klassen der in den Bildern zu sehenden Objekte, sowie ihre *Bounding Box* im Bildkoordinatensystem.

**Ausgabe:** Anzahl der erkannten Objekte in einem neuen Bild, sowie deren Metadaten.

Zur Extraktion wird ein allgemeines Vorgehen entsprechenden der Abbildung angenommen:

<!-- style="display: block; margin-left: auto; margin-right: auto; max-width: auto;" -->
```    ascii
  +-------------+   +---------------+   +-------------+
  |             |   |               |   |             |
  |   Dateien   +-->|   Objekt-     +-->|  Ergebnis   |
  |    (.jpg)   |   |   detektion   |   | (.jpg/.xml) |  
  |             |   |               |   |             |
  +-------------+   +---------------+   +-------------+
```
Zur Vereinfachung können drei Phasen unterschieden werden:

1. Klassifikation von Bildern:
   * Es ist im Bild immer genau ein Objekt zu sehen

2. Detektion von Objekten in Bildern:
   * Suchen von Objekten im Bild und bilden einer *Bounding Box*

3. Objekterkennung:
   * Kombination von 2. und 1.

**Daten**

Die Daten, die euch zur Verfügung stehen, setzen sich aus einem Trainingsdatenset und Validierungsdaten zusammen. Zur Bestimmung der Güte eurer Klassifikatoren, werden wir ein separates Set von Testdaten bereithalten. Ihr findet die Daten [hier](???)

**Bewertung der Objektdetektoren**

Zur Bewertung der implemetierten Detektoren wird im Laufe des Semesters ein Evaluationsskript veröffentlicht. Nach derzeitigem Stand wird es eine Möglichkeit geben, dieses automatisiert während der Entwicklung der Detektoren wiederholt auszuführen.

**Zielsystem**

Das Zielsystem ist ein Ubuntu 18.04. Es wird darüber hinaus aber auch die Möglichkeit geben ein Docker-Image zu spezifizieren. In dieses Image wird eine Nvidia-Grafikkarte (CUDA) gelinkt werden, sodass auch Grafikkarten zur Beschleunigung der Objekterkennung zur Verfügung stehen.

**Erste Schritte**

Verschafft euch zunächst einen Überblick über die Daten:

* Wie sind diese strukturiert?
* Bietet sich das Format (Pascal VOC) an?
* Wie könnt/müsst ihr die Daten vorbereiten um sie für eine Objekterkennung nutzen zu können?

Möglicherweise bietet sich die Generierung einer Datenbank an, die dynamisch angefragt werden kann, sodass ihr auch Spezialfälle einfach testen könnt (z.B. Objekte eines bestimmten Typs).

### Spezifische Module für ERIKA

* **Statemachine** - Überwachung und Darstellung des Zustands in dem sich der Roboter befindet
* **Wahrnehmung** - Sensorische Wahrnehmung des Roboter und entsprechende Verarbeitung (z.B. Filter)
* **Navigation** - Planung und Ausführung von Bewegungen des Roboters basierend auf den Daten des aktuellen Weltmodells
* **Manipulator** - Greifen von detektierten Objekten (siehe Aufgabenkomplex 1)


## Ablaufplan

**Wöchentliche Meetings:**
| Aufgabenkomplex | Meeting               |
|:----------------|:----------------------|
| 1               | Montags 09:15 - 10:45 |
| 2               | Montags 16:00 - 17:30 |

**Bei jedem Meeting wird ein Mitglied von jedem Team kurz die Fortschritte zusammenfassen:**
* Welche Ziele wurden für die Woche gesetzt?
* Welche Ziele wurden erreicht, welche nicht? Warum?
* Welche Ziele gibt es für die kommende Woche?

Jedes Team sollte diese Fortschritte, genannten Ziele und Probleme entsprechend dokumentieren. Hier bieten sich Wikis, Issues, Protokolle, ... an!

Daraufhin wird es die Möglichkeit geben über die aktuellen Probleme zu diskutieren, oder gegebenenfalls einen individuellen Termin zur Lösung schwierigerer Fragestellungen zu vereinbaren.
Zusätzlich wird jedes Team drei Vorträge halten.

**Vorträge**

* Exposé:

  * Motivation des Projektes
  * Stand der Technik (nutzt dazu auch die Teambeschreibungs-Paper des RoboCup@Work [Link](???))
  * Zeitliche und inhaltliche Planung des Projektes (Meilensteinplanung)

* Zwischenstand:

  * Vorstellung der (angestrebten) Softwarestruktur
  * Stand der Implementierung
  * Wo steht ihr bezüglich des Plans? Sind Anpassungen notwendig?

* Abschlussvortrag:
  * Zusammenfassung des Projektes (zeitlich, inhaltlich, konzeptionell)

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
Im Fokus stehen die eingesetzen Techniken und Konzepte, sowie Entscheidungsprozesse zu dokumentieren und zu begründen.

**2. Dokumentation (1/9)**

Ebenfalls von großer Bedeutung bei Softwareprojekten ist die hinreichende Dokumentation der Software.
Dementsprechend fließt auch diese in die Bewertung mit ein.
Entscheidend ist hierbei jedoch, dass (neben den Vorträgen, die auch der Dokumentation dienen) eine Anleitung zur Nutzung der Software sowie für mögliche Weiterentwicklungen entsteht.

**3. Tooling (1/9)**

Neben den dokumentativen Aufgaben kann der Einsatz der richtigen Tools dramatisch zum Erfolg/Misserfolg eines Projektes beitragen.
Dementsprechend sollten (soweit sinnvoll) Tools zur Automatisierung/Unterstützung des Entwicklungsprozesses eingesetzt werden.
Dokumentiert sowohl den Einsatz der Tools, als auch, wie hilfreich ihr diese Empfunden habt.

**4. Softwarearchitektur (1/9)**

Letztlich steht auch die Softwarearchitektur als zentrale Komponent eines Softwareprojekts im Fokus des Semesters.
Hier soll vor allem eine konsistente, intuitive Struktur angestrebt werden.
*Hinweis: Eine Software, die sich schlecht dokumentieren lässt, ist vermutlich nicht intuitiv oder gar schlecht strukturiert!*



**Beispielrechnung:**

| **Vortrag 1**   | **Vortrag 2**    | **Vortrag 3**    | **Dokumentation** | **Tooling**      | **Softwarearchitektur** | **Note** |
|:----------------|:-----------------|:-----------------|:------------------|:-----------------|:------------------------|:---------|
| $1.0 \cdot 2/9$ | $2.3 \cdot  2/9$ | $1.3 \cdot  2/9$ | $2.0 \cdot 1/9$   | $1.3 \cdot  1/9$ | $1.7 \cdot 1/9$         | **1.7**  |
