# Orga
Hi :) 
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
Was sind Roboter?
- Roboter sind Maschinen, die entworfen wurden, um verschiedene Aufgaben automatisch auszuführen. Dabei besteht ein Zusammenspiel zwischen Sensorik, Aktorik und einem Controller
- Automatisierung

Welche Disziplinen sind Teil der Robotik?
- Mechanics
- Electronics
- Computer Science

Welche mechanischen Komponenten eines Roboters können unterschieden werden?
- Links
- Joints
- Actuators: usually either rotary or linear
- DOF: Degrees of freedom

Was sind Freiheitsgrade (DOF - degrees of freedom) eines Roboters?
Die Freiheitsgrade (DOF - Degrees of Freedom) eines Roboters beschreiben die Anzahl der unabhängigen Bewegungsmöglichkeiten, die der Roboter hat. Jeder Freiheitsgrad entspricht einer unabhängigen Achse, entlang der sich der Roboter bewegen oder um die er sich drehen kann.

Was meint der Begriff "autonomes Fahren (AF/AD)"?
- Abhängig welches Level des autonomen Fahren man betrachtet
- unbemanntes Fahren möglich
- findet auch Möglichkeiten zu fahren in unbekannten Umgebungen

Was sind "Fahrerassistenzsysteme"?
- Vorstufe zum AF - Nicht AF
- Spurhalteassistenzsystem
### Questions II
Gibt es einen Zusammenhang zwischen AF/AD und Robotik?

Wie viele Freiheitsgrade hat ein autonomes Fahrzeug?
Drei:
1. **Längsbewegung (Vorwärts/Rückwärts)**: Kontrolle über die Geschwindigkeit des Fahrzeugs.
2. **Querbewegung (Seitwärts)**: Während Autos nicht seitlich fahren können, ermöglicht die Lenkung die seitliche Manövrierfähigkeit durch Spurwechsel oder beim Navigieren in Kurven.
3. **Rotation um die vertikale Achse**: Die Lenkbewegung, die das Fahrzeug in die gewünschte Richtung dreht.

Was sind Modelle? / What are "models"?
- For us, a robot model contains (at least):
	- a description of central mechanical components and properties
	- a description of actuated components and sensor positions and orientations

- For us, a robot model is needed to:
	- be able to use the actuation of the robot at all → i.e. to know where to actuate how much in which direction
	- to know how to “read”/to understand the sensor data at all
	-  to be able to design and build the robot
	- to be able to simulate the robot

Wofür brauchen wir Modelle? (Modelle→ URDF)

Welche Roboterkonstruktionsklassen können unterschieden werden?
- fixed-base robots
- mobile robots
- parallel robot mechanisms
### Questions III
Welche Arten von Aktuatoren können unterschieden werden?
- Es kann zwischen rotierenden und linearen Aktuatoren unterschieden werden.

Was sind verbreitete Robotik-Frameworks?
- Rock (Robotics Toolkit) und ROS (Robot Operating System)

Was sind ROS computation concepts?
- ROS nodes: processes that use ROS API to perform computations,
- ROS master: intermediate program that connects ROS nodes
- ROS parameter server: program that normally runs along with the ROS master to store and distribute public or private parameters
- ROS topics: named buses in which ROS nodes can send a message, a node can publish or subscribe multiple topics
- ROS message: see above, existing messages based on primitive data types, own messages possible as well
- ROS service: a service call is function, called when a client sends a request (request/reply mechanism in contrast to ROS topics), server node: creates/offers a service call, client node: calls the service
- ROS bags: method to save and play back ROS topics, e.g., to log data from a robot

Was sind ROS command tools?
- roscore, rostopic, rosnode, etc., um ROS-Befehle über die Konsole einzugeben.

Was sind Unterschiede zwischen ROS1 und ROS2?
	ROS2 wurde von Grund auf neugebaut, um auch Anwendung im kommerziellen Bereich zu finden und sollte deshalb die folgenden Design Voraussetzungen erfüllen:
- Security: Verschlüsselung
- Embedded systems: Es soll auch auf eingebetteten Systemen laufen
- Diverse networks: Es soll zwischen verschiedenen Netzwerken kommunizieren können
- Real-time computing: Es muss Berechnungen in Echtzeit ausführen können
- Product Readiness: Es muss bestimmte Sicherheits- und Industriestandards erfüllen
### Questions IV
Womit beschäftigt sich die Regelungstechnik?
	Die Regelungstheorie untersucht die Steuerung einer Anlage durch einen Regler (Controller).

Ein Controllertyp sind PID-Controller. Wofür stehen P, I und D?
1. **P - Proportional**: Der proportionale Teil reagiert auf den aktuellen Fehler, der die Differenz zwischen dem gewünschten Sollwert (Setpoint) und dem tatsächlichen Istwert (Messwert) ist. Der proportionale Term berechnet eine Steueraktion, die proportional zu diesem Fehler ist. Das bedeutet, je größer der Fehler, desto größer die Steueraktion. Dies ermöglicht eine schnelle Reaktion auf Änderungen, kann aber zu einem ständigen Über- oder Unterschwingen führen, da der proportionale Term allein den Fehler nicht auf Null reduzieren kann, ohne dass eine gewisse Differenz verbleibt.
2. **I - Integral**: Der integrale Teil summiert die Fehlerwerte über die Zeit und integriert sie, was bedeutet, dass er die kumulierte Abweichung vom Sollwert berücksichtigt. Dies ermöglicht dem Regler, auch langfristige, anhaltende Fehler auszugleichen, die der proportionale Teil nicht vollständig korrigieren kann. Der integrale Term hilft, den stationären Fehler (Steady-State Error) zu eliminieren, kann aber, wenn er nicht richtig eingestellt ist, zu einer Überreaktion und Instabilität führen (bekannt als Integral Windup).
3. **D - Differential**: Der differentiale Teil reagiert auf die Änderungsrate des Fehlers, indem er dessen Ableitung über die Zeit berechnet. Er trägt dazu bei, die zukünftige Richtung des Fehlers vorherzusagen und die Systemreaktion zu glätten, besonders in Bezug auf das Überschwingen und die Schwingungsneigung. Indem der D-Term auf die Geschwindigkeit der Fehleränderung reagiert, hilft er, das System schneller zu stabilisieren und eine übermäßige Reaktion des Reglers zu verhindern.

Was sind Vorgehensweisen zur PID-Parameterbestimmung?
1. Einstellregeln Ziegler & Nichols: Auf Basis:
	a) Modell der Regelstrecke oder 
	b) 1. P-Regler, 2. KR hoch bis KR,krit instabil, d.h. Strecke schwingt mit Tkrit, 3. dann Parameter aus Tabelle ablesen.
2. Einstellregeln Chien, Hrones, Reswick:
	Sprungantwort benötigt → KS (bei y(t)=1), Wendepunkt, Tu und Tg z.B. graphisch ablesen, dann Parameter aus Tabelle bestimmen.

Was wird in der Robotik mit "Kinematik" bezeichnet?
In der Robotik bezieht sich der Begriff "Kinematik" auf die Untersuchung der Bewegung von Robotern ohne Berücksichtigung der Kräfte, die diese Bewegungen verursachen. Die Kinematik beschäftigt sich mit den geometrischen Aspekten der Bewegung, analysiert die Position, Geschwindigkeit und Beschleunigung der Teile eines Roboters und wie diese Größen durch die Aktuatorbewegungen beeinflusst werden. Es gibt zwei Hauptbereiche der Kinematik in der Robotik:

1. **Vorwärtskinematik (Forward Kinematics - FK):** Hierbei geht es darum, auf der Basis gegebener Gelenkwinkel (oder Positionen der Antriebselemente) die Position und Orientierung des Endeffektors (zum Beispiel die Hand oder das Werkzeug eines Roboters) zu bestimmen. Bei der Vorwärtskinematik sind die Eingaben die Winkel oder Positionen der Gelenke des Roboters, und die Ausgaben sind die Position und Orientierung des Endeffektors im Raum.
    
2. **Rückwärtskinematik (Inverse Kinematics - IK):** Dies ist der umgekehrte Prozess der Vorwärtskinematik. Hier wird auf Basis einer gewünschten Position und Orientierung des Endeffektors die notwendigen Gelenkwinkel oder Positionen der Antriebselemente des Roboters berechnet. Bei der Rückwärtskinematik sind die Eingaben die gewünschte Position und Orientierung des Endeffektors, und die Ausgaben sind die dafür erforderlichen Winkel oder Positionen der Gelenke.
## Kapitel 2
### Questions I
Nennen Sie zwei typische Arten von Gelenken (joints).
- **Drehgelenke (Rotary Joints oder Revolute Joints):** Diese Gelenktypen erlauben eine Rotationsbewegung um eine einzige Achse.
- **Schubgelenke (Prismatic Joints):** Schubgelenke ermöglichen eine lineare Bewegung entlang einer Achse.

Welche Stufen von Autonomie können nach SAE J3016 unterschieden werden?
Level 0 bis Level 5 (6 Level)
![Alt-Text](Pasted%20image%2020240229171622.png)

Welche Programme zur Verkehrssimulation kennen Sie?
- Gazebo: commonly used with ROS, general 3D simulator incl. physics, no special focus on street env. / vehicles
- Carla: focus and well supported street env. + vehicles (existing assets), ROS-bridge existing, GPU needed
- Udacity self-driving-car-sim: also focus on street environments + vehicles, uses Unity
- Unity: game engine, 3D and physics
- TORCS: 3D racing simulator, used also in ML applications (Chen et al. 2015) (Video + Paper)
- Commercial simulators: Especially when finite element method (FEM) or computational fluid dynamics (CFD) is needed (e.g., for crash or wind resistance simulation)

Wann braucht ein Roboter ein Umgebungsmodell und wieso muss er sich darin lokalisieren?
- Ein Roboter benötigt ein Umgebungsmodell und muss sich darin lokalisieren, um effektiv und autonom in seiner Umgebung agieren zu können. Dies ist insbesondere in komplexen oder unbekannten Umgebungen wichtig, in denen der Roboter Aufgaben ausführen muss, die eine Interaktion mit der Umgebung erfordern.
### Questions II
Was ist der Unterschied zwischen propriozeptiven und extereozeptiven Sensoren? Nennen Sie jeweils Beispiele!
- Propriozeptive Sensoren → Eigenwahrnehmung (z. B. Gyroskop, Beschleunigungssensor).
- Extereozeptive Sensoren → Umweltwahrnehmung (z. B. Kamera, LIDAR, Ultraschallsensor).

Was ist Odometrie?
- Die Odometrie ist eine Unterklasse (der propriozeptiven, sehr selten der exterozeptiven) Sensoren, die Informationen über die zurückgelegte Wegstrecke liefern.

Was ist ein LiDAR-Sensor?
- Ein LiDAR-Sensor (Light Detection and Ranging) ist ein Fernmesssystem, das Licht in Form von gepulsten Lasern verwendet, um Entfernungen zu messen und damit räumliche Informationen über die Umgebung zu sammeln. LiDAR wird in verschiedenen Anwendungsbereichen eingesetzt, darunter Geologie und Bodenkunde, Forstwirtschaft, Archäologie, Umweltüberwachung, Landwirtschaft, und insbesondere in der Robotik und im autonomen Fahren.

Was sind weitere Sensoren autonomer Fahrzeuge?
- Radar
- Ultraschall
- Kamera
- GNSS (global navigation satellite systems)
- IMU (Inertial Measurement Unit)
## Kapitel 3
### Questions I
Was ist eine Standardform zur Beschreibung von Roboterkinematiken?  bzw.: Warum werden Roboter nicht beliebig/wahlfrei entworfen sondern mit bestimmten Einschränkungen?

Was ist der Unterschied zwischen Vorwärts- und inverser Kinematik?
- Die Vorwärtskinematik ist ein direkter Prozess, bei dem die Ausgangsposition der Gelenke bekannt ist und die Position des Endeffektors berechnet wird.
- Die inverse Kinematik ist ein umgekehrter Prozess, bei dem die gewünschte Position des Endeffektors bekannt ist und die erforderlichen Gelenkpositionen berechnet werden müssen, um diese Endeffektorposition zu erreichen. Inverse Kinematik ist oft komplexer, da es in der Regel mehrere mögliche Lösungen für ein gegebenes Ziel gibt, was die Auswahl der optimalen Lösung erforderlich macht.

Welche Arten von Rädern sind bei Robotern zu finden?
- standard wheel
- caster wheel (Schlepprad), spherical wheel (ball)
- leg-like wheel: Active Media, DFKI
- swedish wheels (omnidirectional wheel, Mecanum wheel)
### Questions II
Wofür steht SLAM, was ist damit gemeint?
- Simultaneous Localization And Mapping
- SLAM steht für "Simultaneous Localization and Mapping" (Simultane Lokalisierung und Kartierung). Es handelt sich um ein kritisches Konzept in der Robotik und der autonomen Navigation, das darauf abzielt, dass ein Roboter oder ein autonomes Fahrzeug seine eigene Position in einer unbekannten Umgebung erkennt und gleichzeitig eine Karte dieser Umgebung erstellt. SLAM ist besonders wichtig in Situationen, in denen keine vordefinierten oder genauen Karten verfügbar sind, wie bei der Erkundung unbekannter Gebiete, in Gebäuden oder in dynamisch veränderlichen Umgebungen.
-  Kernkomponenten von SLAM:
	- **Lokalisierung:** Bestimmung der Position und Orientierung des Roboters in Bezug auf seine Umgebung. Dies beinhaltet die Schätzung der aktuellen Lage des Roboters, oft relativ zu einem Startpunkt oder auf Basis von Landmarken in der Umgebung.
    - **Kartierung:** Erstellung einer Karte der Umgebung, die der Roboter erkundet. Diese Karte kann aus verschiedenen Elementen bestehen, einschließlich der räumlichen Anordnung von Hindernissen, Wegen und markanten Punkten.
- Funktionsweise von SLAM:
	- SLAM-Systeme nutzen eine Vielzahl von Sensoren (wie Kameras, LiDAR, Ultraschall, Inertialsensoren) und Algorithmen, um Daten über die Umgebung zu sammeln und zu verarbeiten. Diese Daten werden verwendet, um die Bewegungen des Roboters zu schätzen und gleichzeitig eine Karte der Umgebung zu generieren. Die Herausforderung bei SLAM besteht darin, die Ungewissheit und Ungenauigkeiten zu bewältigen, die mit der Messung und der Bewegung in einer unbekannten Umgebung einhergehen.

ICP und RANSAC können innerhalb von SLAM verwendet werden. Beschreiben Sie beide grob.

Beschreiben Sie grob die Idee eines Kalman-Filters!

Was ist ein Particle Filter? Aus welchen Schritten besteht dessen Berechnung?
### Questions III
Was ist GMapping, beschreiben Sie es grob! Welches Verfahren wird von GMapping verwendet?

Was ist HectorSLAM? Beschreiben Sie es grob!

Schauen Sie sich den zugehörigen Praktikumszetteln an. Welche Erkenntnisse hatten Sie im Praktikum?
## Kapitel 4
### Questions I
Was ist "Random Walk"? Wo kann es eingesetzt werden?
Was ist "Dead-Reckoning"? Was sind Nachteile dieses Verfahrens?
Welche Arten von Karten können in der Robotik unterschieden werden?
Was sind "HD-Maps"?
Was ist "Quer-" und "Längsführung"?
### Questions II
Was ist eine "Ackermann-Lenkung"?
Was ist mit "Pure Pursuit" gemeint?
Beschreiben Sie kurz ein alternatives Verfahren zu "Pure Pursuit"!
Welche Verfahren zur Kommunikation zwischen Fahrzeugen und zwischen Fahrzeugen und Infrastruktur kennen Sie?
### Questions III
Was ist der Unterschied zwischen globaler und lokaler Navigation? Was ist mit Hindernisvermeidung gemeint?
Beschreiben Sie die Pfadplanung mittels Dijkstra oder Greedy Best First Search!
Was ist der Unterschied zwischen der Pfadplanung nach Dijkstra und mittels A*?
Was ist der Vorteil von D* verglichen mit A*?
### Questions IV
Schauen Sie sich den zugehörigen Praktikumszettel an. Welche Erkenntnisse hatten Sie im Praktikum?
## Kapitel 5
### Questions I
Welche rechtlichen Probleme gibt oder gab es im Zusammenhang mit dem autonomen Fahren?
Kennen Sie ein Beispiel für Anpassung von Gesetzen für das autonome Fahren?
## Kapitel 6
### Questions I
Beschreiben Sie die Robotersteuerungsarchitekturen "Sense-Plan-Act"  und die  "Subsumption-Architektur"!
Welche Funktion haben jeweils die Schichten der "3T-Architektur"?
Was sind zwei verbreitete Kommunikationsvarianten der Middleware?
Was sind "Verhalten" in der verhaltensbasierten Steuerung?
### Questions II
Beschreiben Sie die "Behavioural Control"-Schicht!
Beschreiben Sie die "Executive"-Schicht!
Beschreiben Sie die "Planning"-Schicht!
Was ist in der Robotik mit "deliberativer" und "reaktiver" Steuerung gemeint?
Schauen Sie sich den zugehörigen Praktikumszettel an. Welche Erkenntnisse hatten Sie im Praktikum?
