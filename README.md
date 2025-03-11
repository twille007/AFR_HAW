# Orga
## Inhalt der Prüfung
- Stoff der Vorlesungen
- Stoff der Praktika
- (Eigenes Paper)
## Erlaubte Hilfsmittel
- Es darf ein doppelseitiges handbeschriebenes Blatt Papier mitgenommen werden.
## Termin der Prüfung
Wir können ein/zwei Tage vor Ihrem Prüfungstermin einmal versuchen, schon die genauere Prüfungszeit (d.h. die Prüfungsreihenfolge) festzulegen. Ich schreibe Sie dazu ein, zwei Tage vor der Prüfung einmal per Mail an. Mal schauen, ob das klappt. Falls nicht/im Zweifelsfall gilt wieder, dass Sie zu Beginn Ihres Prüfungszeitraums/-termins zum Prüfungsraum bzw. in das Meeting im General/Allgemein-Kanal im MS-Teams-Team kommen und wir dann die Zeiten absprechen.
## Misc
- Die Themen "Bio-Inspired Control" und "Cooperative Robotics" sind nur zur Info auf den Folien sind nicht prüfungsrelevant.
# Prüfungsrelevant
## Kapitel 1 - Introduction
### Questions I
#### Was sind Roboter?
- Roboter sind Maschinen, die entworfen wurden, um verschiedene Aufgaben automatisch auszuführen. Dabei besteht ein Zusammenspiel zwischen Sensorik, Aktorik und einem Controller
- Automatisierung

#### Welche Disziplinen sind Teil der Robotik?
- Mechanics
- Electronics
- Computer Science

#### Welche mechanischen Komponenten eines Roboters können unterschieden werden?
- Links (Glieder)
- Joints (Gelenke)
- Actuators (Aktoren): usually either rotary or linear

#### Was sind Freiheitsgrade (DOF - degrees of freedom) eines Roboters?
Die Freiheitsgrade (DOF - Degrees of Freedom) eines Roboters beschreiben die Anzahl der unabhängigen Bewegungsmöglichkeiten, die der Roboter hat. Jeder Freiheitsgrad entspricht einer unabhängigen Achse, entlang der sich der Roboter bewegen oder um die er sich drehen kann.

#### Was meint der Begriff "autonomes Fahren (AF/AD)"?
- Abhängig welches Level des autonomen Fahren man betrachtet
- unbemanntes Fahren möglich
- findet auch Möglichkeiten zu fahren in unbekannten Umgebungen

#### Was sind "Fahrerassistenzsysteme"?
- Vorstufe zum AF - Nicht AF
- Spurhalteassistenzsystem
### Questions II
#### Gibt es einen Zusammenhang zwischen AF/AD und Robotik?
Ein autonomes Fahrzeug kann als eine spezielle Form eines mobilen Roboters betrachtet werden. Es besitzt Sensoren, Aktoren und Algorithmen zur autonomen Entscheidungsfindung, ähnlich wie ein Roboterarm oder ein Laufroboter – nur in größerem Maßstab und mit höheren Sicherheitskriterien.

#### Wie viele Freiheitsgrade hat ein autonomes Fahrzeug?
Drei:
1. **Längsbewegung (Vorwärts/Rückwärts)**: Kontrolle über die Geschwindigkeit des Fahrzeugs.
2. **Querbewegung (Seitwärts)**: Während Autos nicht seitlich fahren können, ermöglicht die Lenkung die seitliche Manövrierfähigkeit durch Spurwechsel oder beim Navigieren in Kurven.
3. **Rotation um die vertikale Achse**: Die Lenkbewegung, die das Fahrzeug in die gewünschte Richtung dreht.

#### Was sind Modelle? / What are "models"?
Für uns umfasst ein Robotermodell (mindestens):
  - eine Beschreibung der zentralen mechanischen Komponenten und Eigenschaften
  - eine Beschreibung der angetriebenen Komponenten sowie der Positionen und Ausrichtungen der Sensoren

#### Wofür brauchen wir Modelle? (Modelle→ URDF)
Modelle (insbesondere URDF - Unified Robot Description Format) sind essenziell, um Roboter zu verstehen, zu simulieren, zu steuern und Sensoren zu nutzen. Sie dienen als digitale Repräsentation des Roboters und ermöglichen eine effiziente Entwicklung, Fehlersuche und Optimierung.

#### Welche Roboterkonstruktionsklassen können unterschieden werden?
- fixed-base robots (Stationäre Roboter)
- mobile robots (Mobile Roboter)
- parallel robot mechanisms (Parallele Robotermechanismen - Roboter mit mehreren kinematischen Ketten)

### Questions III
#### Welche Arten von Aktuatoren können unterschieden werden?
- Es kann zwischen rotierenden und linearen Aktuatoren unterschieden werden.

#### Was sind verbreitete Robotik-Frameworks?
- Rock (Robotics Toolkit) und ROS (Robot Operating System)

#### Was sind ROS computation concepts?
- ROS nodes: processes that use ROS API to perform computations,
- ROS master: intermediate program that connects ROS nodes
- ROS parameter server: program that normally runs along with the ROS master to store and distribute public or private parameters
- ROS topics: named buses in which ROS nodes can send a message, a node can publish or subscribe multiple topics
- ROS message: see above, existing messages based on primitive data types, own messages possible as well
- ROS service: a service call is function, called when a client sends a request (request/reply mechanism in contrast to ROS topics), server node: creates/offers a service call, client node: calls the service
- ROS bags: method to save and play back ROS topics, e.g., to log data from a robot

#### Was sind ROS command tools?
- roscore, rostopic, rosnode, etc., um ROS-Befehle über die Konsole einzugeben.

#### Was sind Unterschiede zwischen ROS1 und ROS2?
ROS2 wurde von Grund auf neugebaut, um auch Anwendung im kommerziellen Bereich zu finden und sollte deshalb die folgenden Design Voraussetzungen erfüllen:
- Security: Verschlüsselung
- Embedded systems: Es soll auch auf eingebetteten Systemen laufen
- Diverse networks: Es soll zwischen verschiedenen Netzwerken kommunizieren können
- Real-time computing: Es muss Berechnungen in Echtzeit ausführen können
- Product Readiness: Es muss bestimmte Sicherheits- und Industriestandards erfüllen

### Questions IV
#### Womit beschäftigt sich die Regelungstechnik?
Die Regelungstheorie untersucht die Steuerung einer Anlage durch einen Regler (Controller).

#### Ein Controllertyp sind PID-Controller. Wofür stehen P, I und D?
1. **P - Proportional**: Der proportionale Teil reagiert auf den aktuellen Fehler, der die Differenz zwischen dem gewünschten Sollwert (Setpoint) und dem tatsächlichen Istwert (Messwert) ist. Der proportionale Term berechnet eine Steueraktion, die proportional zu diesem Fehler ist. Das bedeutet, je größer der Fehler, desto größer die Steueraktion. Dies ermöglicht eine schnelle Reaktion auf Änderungen, kann aber zu einem ständigen Über- oder Unterschwingen führen, da der proportionale Term allein den Fehler nicht auf Null reduzieren kann, ohne dass eine gewisse Differenz verbleibt.
2. **I - Integral**: Der integrale Teil summiert die Fehlerwerte über die Zeit und integriert sie, was bedeutet, dass er die kumulierte Abweichung vom Sollwert berücksichtigt. Dies ermöglicht dem Regler, auch langfristige, anhaltende Fehler auszugleichen, die der proportionale Teil nicht vollständig korrigieren kann. Der integrale Term hilft, den stationären Fehler (Steady-State Error) zu eliminieren, kann aber, wenn er nicht richtig eingestellt ist, zu einer Überreaktion und Instabilität führen (bekannt als Integral Windup).
3. **D - Differential**: Der differentiale Teil reagiert auf die Änderungsrate des Fehlers, indem er dessen Ableitung über die Zeit berechnet. Er trägt dazu bei, die zukünftige Richtung des Fehlers vorherzusagen und die Systemreaktion zu glätten, besonders in Bezug auf das Überschwingen und die Schwingungsneigung. Indem der D-Term auf die Geschwindigkeit der Fehleränderung reagiert, hilft er, das System schneller zu stabilisieren und eine übermäßige Reaktion des Reglers zu verhindern.

#### Was sind Vorgehensweisen zur PID-Parameterbestimmung?
1. Einstellregeln Ziegler & Nichols: Auf Basis:
	a) Modell der Regelstrecke oder 
	b) 1. P-Regler, 2. KR hoch bis KR,krit instabil, d.h. Strecke schwingt mit Tkrit, 3. dann Parameter aus Tabelle ablesen.
2. Einstellregeln Chien, Hrones, Reswick:
	Sprungantwort benötigt → KS (bei y(t)=1), Wendepunkt, Tu und Tg z.B. graphisch ablesen, dann Parameter aus Tabelle bestimmen.

#### Was wird in der Robotik mit "Kinematik" bezeichnet?
In der Robotik bezieht sich der Begriff "Kinematik" auf die Untersuchung der Bewegung von Robotern ohne Berücksichtigung der Kräfte, die diese Bewegungen verursachen. Die Kinematik beschäftigt sich mit den geometrischen Aspekten der Bewegung, analysiert die Position, Geschwindigkeit und Beschleunigung der Teile eines Roboters und wie diese Größen durch die Aktuatorbewegungen beeinflusst werden. Es gibt zwei Hauptbereiche der Kinematik in der Robotik:

1. **Vorwärtskinematik (Forward Kinematics - FK):** Hierbei geht es darum, auf der Basis gegebener Gelenkwinkel (oder Positionen der Antriebselemente) die Position und Orientierung des Endeffektors (zum Beispiel die Hand oder das Werkzeug eines Roboters) zu bestimmen. Bei der Vorwärtskinematik sind die Eingaben die Winkel oder Positionen der Gelenke des Roboters, und die Ausgaben sind die Position und Orientierung des Endeffektors im Raum.
    
2. **Rückwärtskinematik (Inverse Kinematics - IK):** Dies ist der umgekehrte Prozess der Vorwärtskinematik. Hier wird auf Basis einer gewünschten Position und Orientierung des Endeffektors die notwendigen Gelenkwinkel oder Positionen der Antriebselemente des Roboters berechnet. Bei der Rückwärtskinematik sind die Eingaben die gewünschte Position und Orientierung des Endeffektors, und die Ausgaben sind die dafür erforderlichen Winkel oder Positionen der Gelenke.
## Kapitel 2
### Questions I
#### Nennen Sie zwei typische Arten von Gelenken (joints).
- Drehgelenke (Rotary Joints oder Revolute Joints): Diese Gelenktypen erlauben eine Rotationsbewegung um eine einzige Achse.
- Schubgelenke (Prismatic Joints): Schubgelenke ermöglichen eine lineare Bewegung entlang einer Achse.

#### Welche Stufen von Autonomie können nach SAE J3016 unterschieden werden?
Level 0 bis Level 5 (6 Level)
![SAE_J3016](media/SAE_J3016)

#### Welche Programme zur Verkehrssimulation kennen Sie?
- Gazebo: commonly used with ROS, general 3D simulator incl. physics, no special focus on street env. / vehicles
- Carla: focus and well supported street env. + vehicles (existing assets), ROS-bridge existing, GPU needed
- Udacity self-driving-car-sim: also focus on street environments + vehicles, uses Unity
- Unity: game engine, 3D and physics
- TORCS: 3D racing simulator, used also in ML applications (Chen et al. 2015) (Video + Paper)
- Commercial simulators: Especially when finite element method (FEM) or computational fluid dynamics (CFD) is needed (e.g., for crash or wind resistance simulation)

#### Wann braucht ein Roboter ein Umgebungsmodell und wieso muss er sich darin lokalisieren?
- Ein Roboter benötigt ein Umgebungsmodell und muss sich darin lokalisieren, um effektiv und autonom in seiner Umgebung agieren zu können. Dies ist insbesondere in komplexen oder unbekannten Umgebungen wichtig, in denen der Roboter Aufgaben ausführen muss, die eine Interaktion mit der Umgebung erfordern.

### Questions II
#### Was ist der Unterschied zwischen propriozeptiven und extereozeptiven Sensoren? Nennen Sie jeweils Beispiele!
- Propriozeptive Sensoren → Eigenwahrnehmung (z. B. Gyroskop, Beschleunigungssensor).
- Extereozeptive Sensoren → Umweltwahrnehmung (z. B. Kamera, LIDAR, Ultraschallsensor).

#### Was ist Odometrie?
- Die Odometrie ist eine Unterklasse (der propriozeptiven, sehr selten der exterozeptiven) Sensoren, die Informationen über die zurückgelegte Wegstrecke liefern.

#### Was ist ein LiDAR-Sensor?
- Ein LiDAR-Sensor (Light Detection and Ranging) ist ein Fernmesssystem, das Licht in Form von gepulsten Lasern verwendet, um Entfernungen zu messen und damit räumliche Informationen über die Umgebung zu sammeln. LiDAR wird in verschiedenen Anwendungsbereichen eingesetzt, darunter Geologie und Bodenkunde, Forstwirtschaft, Archäologie, Umweltüberwachung, Landwirtschaft, und insbesondere in der Robotik und im autonomen Fahren.

#### Was sind weitere Sensoren autonomer Fahrzeuge?
- Radar
- Ultraschall
- Kamera
- GNSS (global navigation satellite systems)
- IMU (Inertial Measurement Unit)

## Kapitel 3
### Questions I
#### Nennen Sie zwei typische Arten von Gelenken!
- Drehgelenk (Revolute Joint) (Ermöglicht eine Rotation um eine feste Achse.)
- Schubgelenk (Prismatic Joint) (Ermöglicht eine lineare Bewegung entlang einer Achse (Translation statt Rotation).)

#### Was ist eine Standardform zur Beschreibung von Roboterkinematiken?  bzw.: Warum werden Roboter nicht beliebig/wahlfrei entworfen sondern mit bestimmten Einschränkungen?
- TODO

#### Was ist der Unterschied zwischen Vorwärts- und inverser Kinematik?
- Die Vorwärtskinematik ist ein direkter Prozess, bei dem die Ausgangsposition der Gelenke bekannt ist und die Position des Endeffektors berechnet wird.
- Die inverse Kinematik ist ein umgekehrter Prozess, bei dem die gewünschte Position des Endeffektors bekannt ist und die erforderlichen Gelenkpositionen berechnet werden müssen, um diese Endeffektorposition zu erreichen. Inverse Kinematik ist oft komplexer, da es in der Regel mehrere mögliche Lösungen für ein gegebenes Ziel gibt, was die Auswahl der optimalen Lösung erforderlich macht.

#### Welche Arten von Rädern sind bei Robotern zu finden?
- standard wheel
- caster wheel (Schlepprad), spherical wheel (ball)
- leg-like wheel: Active Media, DFKI
- swedish wheels (omnidirectional wheel, Mecanum wheel)
### Questions II
#### Wofür steht SLAM, was ist damit gemeint?
- Simultaneous Localization And Mapping
- SLAM steht für "Simultaneous Localization and Mapping" (Simultane Lokalisierung und Kartierung). Es handelt sich um ein kritisches Konzept in der Robotik und der autonomen Navigation, das darauf abzielt, dass ein Roboter oder ein autonomes Fahrzeug seine eigene Position in einer unbekannten Umgebung erkennt und gleichzeitig eine Karte dieser Umgebung erstellt. SLAM ist besonders wichtig in Situationen, in denen keine vordefinierten oder genauen Karten verfügbar sind, wie bei der Erkundung unbekannter Gebiete, in Gebäuden oder in dynamisch veränderlichen Umgebungen.
-  Kernkomponenten von SLAM:
	- **Lokalisierung:** Bestimmung der Position und Orientierung des Roboters in Bezug auf seine Umgebung. Dies beinhaltet die Schätzung der aktuellen Lage des Roboters, oft relativ zu einem Startpunkt oder auf Basis von Landmarken in der Umgebung.
    - **Kartierung:** Erstellung einer Karte der Umgebung, die der Roboter erkundet. Diese Karte kann aus verschiedenen Elementen bestehen, einschließlich der räumlichen Anordnung von Hindernissen, Wegen und markanten Punkten.
- Funktionsweise von SLAM:
	- SLAM-Systeme nutzen eine Vielzahl von Sensoren (wie Kameras, LiDAR, Ultraschall, Inertialsensoren) und Algorithmen, um Daten über die Umgebung zu sammeln und zu verarbeiten. Diese Daten werden verwendet, um die Bewegungen des Roboters zu schätzen und gleichzeitig eine Karte der Umgebung zu generieren. Die Herausforderung bei SLAM besteht darin, die Ungewissheit und Ungenauigkeiten zu bewältigen, die mit der Messung und der Bewegung in einer unbekannten Umgebung einhergehen.

#### ICP und RANSAC können innerhalb von SLAM verwendet werden. Beschreiben Sie beide grob.
ICP wird hauptsächlich zur genauen Ausrichtung von Punktwolken genutzt, wenn eine gute Annäherung der Transformation existiert. RANSAC wird genutzt, um robuste Modelle trotz Ausreißern zu finden, z. B. zur Entfernung falscher Korrespondenzen in der Merkmalsextraktion.

ICP ist ein iterativer Algorithmus zur Registrierung von Punktwolken, d. h., er versucht, zwei Punktwolken (z. B. aus einem LiDAR-Sensor) möglichst gut aufeinander auszurichten.
Funktionsweise von ICP:
- Punktzuordnung: Für jeden Punkt in der Quellpunktwolke wird der nächste Punkt in der Zielpunktwolke gesucht.
- Transformation berechnen: Die optimale Rotations- und Translationsmatrix wird bestimmt, um die Punktwolken möglichst gut auszurichten.
- Transformation anwenden: Die Quellpunktwolke wird entsprechend transformiert.
- Iterationen: Der Prozess wird wiederholt, bis ein Abbruchkriterium (z. B. Konvergenz oder Anzahl der Iterationen) erreicht ist.

RANSAC ist ein robuster Algorithmus zur Schätzung von Modellen in verrauschten Daten, indem er Ausreißer (Outlier) entfernt.
Funktionsweise von RANSAC:
- Zufällige Auswahl: Es werden zufällig eine kleine Anzahl von Punkten gewählt, um ein Modell (z. B. eine Gerade oder Transformation) zu schätzen.
- Konsistenzprüfung: Die restlichen Datenpunkte werden überprüft, ob sie zu diesem Modell passen („Inlier“).
- Wiederholung: Der Prozess wird mehrmals durchgeführt, bis das beste Modell mit den meisten Inliers gefunden ist.

#### Beschreiben Sie grob die Idee eines Kalman-Filters!
Der Kalman-Filter kombiniert zwei Informationsquellen:
- Vorhersage (Prediction) → Ein Modell sagt voraus, wie sich der Zustand eines Systems entwickeln sollte.
- Messung (Update/Correction) → Sensoren liefern neue Messwerte, die aber verrauscht sein können.

Durch die geschickte Gewichtung von Modell und Messung wird die beste Schätzung des tatsächlichen Systemzustands berechnet.

#### Was ist ein Particle Filter? Aus welchen Schritten besteht dessen Berechnung?
Statt den Zustand eines Systems durch eine einzelne Schätzung oder eine Verteilung (wie beim Kalman-Filter) zu beschreiben, verwendet der Partikelfilter eine Menge von Partikeln (Einzelzustände), um eine Wahrscheinlichkeitsverteilung über mögliche Zustände darzustellen.
- Jedes Partikel ist eine mögliche Schätzung des Systemzustands.
- Jedes Partikel hat ein Gewicht, das angibt, wie gut es zur aktuellen Messung passt.
- Durch iterative Anpassung der Partikel wird der wahre Zustand des Systems angenähert.

Ein Partikelfilter besteht aus vier Hauptschritten, die rekursiv wiederholt werden:
1. Initialisierung
   - Eine Menge von NN Partikeln wird zufällig verteilt.
   - Jeder Partikel repräsentiert einen möglichen Zustand des Systems.
   - Falls Vorwissen existiert, können die Partikel aus einer Wahrscheinlichkeitsverteilung gezogen werden.

2. Vorhersage (Prediction)
   - Jedes Partikel wird mit einem dynamischen Modell aktualisiert (z. B. anhand der Bewegungsgleichungen des Roboters).
   - Modellfehler und Unsicherheiten werden durch zufällige Störungen (z. B. Gaussian Noise) berücksichtigt.

3. Gewichtung (Update)
   - Die Sensorwerte werden mit den vorhergesagten Partikeln verglichen.
   - Jedem Partikel wird ein Gewicht basierend auf der Wahrscheinlichkeit zugewiesen, dass es die aktuelle Messung erklärt.
   - Partikel, die gut zur Messung passen, erhalten ein höheres Gewicht.

4. Resampling (Neuziehung)
   - Partikel mit hohen Gewichten werden bevorzugt dupliziert.
   - Partikel mit geringen Gewichten werden verworfen.
   - Dadurch wird die Verteilung neu fokussiert und schlechte Schätzungen entfernt.
   - Nach dem Resampling haben alle Partikel wieder das gleiche Gewicht.

Dieser Zyklus wird kontinuierlich wiederholt, um den Zustand zu schätzen.

### Questions III
#### Was ist GMapping, beschreiben Sie es grob! Welches Verfahren wird von GMapping verwendet?
GMapping ist ein SLAM-Algorithmus (Simultaneous Localization and Mapping), der es einem Roboter ermöglicht, eine Umgebungskarte zu erstellen, während er sich gleichzeitig innerhalb dieser Umgebung lokalisiert. Es wird häufig in der Robotik, insbesondere mit ROS (Robot Operating System), für mobile Roboter verwendet.

GMapping basiert auf einem Rao-Blackwellized Particle Filter (RBPF), einer speziellen Form des Partikelfilters. Hierbei wird der SLAM-Prozess in zwei Teile aufgeteilt:
1. Lokalisierung des Roboters: Die Partikel des Filters repräsentieren mögliche Roboterpositionen und -orientierungen basierend auf Sensordaten (z. B. LiDAR oder Sonar).
2. Kartenaktualisierung: Jede Partikelhypothese enthält eine eigene Kartenrepräsentation, die mit den neuen Sensordaten aktualisiert wird.

Durch die Rao-Blackwellization wird die Berechnung effizienter, indem die Positionsschätzung als Partikelfilter behandelt wird, während die Kartenerstellung mit einem probabilistischen Bayes-Filter durchgeführt wird.

#### Was ist HectorSLAM? Beschreiben Sie es grob!
HectorSLAM ist ein SLAM-Algorithmus (Simultaneous Localization and Mapping), der speziell für Roboter mit hochfrequenten LIDAR-Sensoren entwickelt wurde. Im Gegensatz zu vielen anderen SLAM-Methoden, wie GMapping, benötigt HectorSLAM keine Odometriedaten (z. B. von Radsensoren), sondern arbeitet ausschließlich mit LIDAR-Scans.

HectorSLAM basiert auf einem Scan-Matching-Ansatz, der eine direkte Registrierung der LIDAR-Daten mit einer probabilistischen Karte durchführt. Der zentrale Algorithmus ist die Gauss-Newton-Optimierung, die versucht, die Position des Roboters durch Minimierung der Fehler zwischen aktuellen und vorherigen LIDAR-Scans zu optimieren.

Die Kernkomponenten sind:
1. Scan-Matching mit Occupancy Grid Mapping
   - Jeder neue LIDAR-Scan wird direkt mit der bestehenden Karte abgeglichen.
   - Dafür wird ein multiresolution approach verwendet, bei dem Scans auf mehreren Auflösungsstufen verarbeitet werden.

2. Keine Odometriedaten erforderlich
   - Während andere SLAM-Methoden (z. B. GMapping) oft auf Radodometrie oder IMU-Daten angewiesen sind, funktioniert HectorSLAM nur mit LIDAR.
   - Das ist besonders vorteilhaft für Drohnen oder Roboter ohne präzise Radodometrie.

3. Echtzeitfähigkeit
   - Da HectorSLAM keine Partikelfilter (wie GMapping) verwendet, sondern eine direkte Optimierung durchführt, kann es in Echtzeit auch auf Embedded-Systemen laufen.

#### Schauen Sie sich den zugehörigen Praktikumszetteln an. Welche Erkenntnisse hatten Sie im Praktikum?
- TODO

## Kapitel 4
### Questions I
#### Was ist "Random Walk"? Wo kann es eingesetzt werden?
Ein Random Walk in der Robotik und beim autonomen Fahren beschreibt eine zufällige Bewegung eines Roboters oder Fahrzeugs innerhalb eines gegebenen Raums. Dabei werden Bewegungen oder Entscheidungen ohne gezielte Planung oder Karteninformation getroffen, sondern rein basierend auf Zufallsprinzipien.

Es könnte beim erkunden von unbekannten Gegenden eingesetzt werden.

#### Was ist "Dead-Reckoning"? Was sind Nachteile dieses Verfahrens?
Dead-Reckoning ist eine Navigationsmethode, bei der die aktuelle Position eines Fahrzeugs oder Roboters ausgehend von einer bekannten Startposition und unter Verwendung von Bewegungsinformationen (z. B. Geschwindigkeit, Richtung, Zeit) geschätzt wird.

Nachteile:
- Dead-Reckoning ist rein schätzungsbasiert und kann nicht feststellen, ob die Berechnung fehlerhaft ist.
- Kleine Messfehler in den Sensoren summieren sich mit der Zeit, sodass die geschätzte Position zunehmend ungenauer wird.

#### Welche Arten von Karten können in der Robotik unterschieden werden?
- Line Maps (Linienkarten) – Beschreiben die Umgebung durch Linien, die aus Sensoren wie LIDAR oder Kameras extrahiert werden, ideal für Straßen- und Indoor-Navigation.
- Metrical Maps (Metrische Karten) – Enthalten präzise geometrische Informationen in Form von Rasterkarten (z. B. Occupancy Grid) oder Vektorkarten für genaue Roboterlokalisierung.
- Topological Maps (Topologische Karten) – Repräsentieren die Umgebung als Graph mit Knoten (wichtige Orte) und Kanten (Verbindungen) für effiziente Pfadplanung ohne genaue metrische Koordinaten.
- Landmark-based Maps (Merkmalsbasierte Karten) – Nutzen markante Punkte (Landmarks) wie Verkehrszeichen, Gebäude oder WLAN-Signale zur Orientierung und Navigation ohne vollständige Kartenrekonstruktion.

#### Was sind "HD-Maps"?

#### Was ist "Quer-" und "Längsführung"?

### Questions II
#### Was ist eine "Ackermann-Lenkung"?

#### Was ist mit "Pure Pursuit" gemeint?

#### Beschreiben Sie kurz ein alternatives Verfahren zu "Pure Pursuit"!

#### Welche Verfahren zur Kommunikation zwischen Fahrzeugen und zwischen Fahrzeugen und Infrastruktur kennen Sie?

### Questions III
#### Was ist der Unterschied zwischen globaler und lokaler Navigation? Was ist mit Hindernisvermeidung gemeint?

#### Beschreiben Sie die Pfadplanung mittels Dijkstra oder Greedy Best First Search!

#### Was ist der Unterschied zwischen der Pfadplanung nach Dijkstra und mittels A\*?

#### Was ist der Vorteil von D* verglichen mit A\*?

### Questions IV
#### Schauen Sie sich den zugehörigen Praktikumszettel an. Welche Erkenntnisse hatten Sie im Praktikum?
- TODO

## Kapitel 5
### Questions I
#### Welche rechtlichen Probleme gibt oder gab es im Zusammenhang mit dem autonomen Fahren?

#### Kennen Sie ein Beispiel für Anpassung von Gesetzen für das autonome Fahren?

## Kapitel 6
### Questions I
#### Beschreiben Sie die Robotersteuerungsarchitekturen "Sense-Plan-Act"  und die  "Subsumption-Architektur"!

#### Welche Funktion haben jeweils die Schichten der "3T-Architektur"?

#### Was sind zwei verbreitete Kommunikationsvarianten der Middleware?

#### Was sind "Verhalten" in der verhaltensbasierten Steuerung?

### Questions II
#### Beschreiben Sie die "Behavioural Control"-Schicht!

#### Beschreiben Sie die "Executive"-Schicht!

#### Beschreiben Sie die "Planning"-Schicht!

#### Was ist in der Robotik mit "deliberativer" und "reaktiver" Steuerung gemeint?

#### Schauen Sie sich den zugehörigen Praktikumszettel an. Welche Erkenntnisse hatten Sie im Praktikum?
- TODO
