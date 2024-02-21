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
Was sind Roboter?
Welche Disziplinen sind Teil der Robotik?
Welche mechanischen Komponenten eines Roboters können unterschieden werden?
Was sind Freiheitsgrade (DOF - degrees of freedom) eines Roboters?
Was meint der Begriff "autonomes Fahren (AF/AD)"?
Was sind "Fahrerassistenzsysteme"?
### Questions II
Gibt es einen Zusammenhang zwischen AF/AD und Robotik?
Wie viele Freiheitsgrade hat ein autonomes Fahrzeug?
Was sind Modelle? / What are "models"?
Wofür brauchen wir Modelle? (Modelle→ URDF)
Welche Roboterkonstruktionsklassen können unterschieden werden?
### Questions III
Welche Arten von Aktuatoren können unterschieden werden?
Was sind verbreitete Robotik-Frameworks?
Was sind ROS computation concepts?
Was sind ROS command tools?
Was sind Unterschiede zwischen ROS1 und ROS2?
### Questions IV
Womit beschäftigt sich die Regelungstechnik?
Ein Controllertyp sind PID-Controller. Wofür stehen P, I und D?
Was sind Vorgehensweisen zur PID-Parameterbestimmung?
Was wird in der Robotik mit "Kinematik" bezeichnet?
## Kapitel 2
### Questions I
Nennen Sie zwei typische Arten von Gelenken (joints)
Welche Stufen von Autonomie können nach SAE J3016 unterschieden werden?
Welche Programme zur Verkehrssimulation kennen Sie?
Wann braucht ein Roboter ein Umgebungsmodell und wieso muss er sich darin lokalisieren?
### Questions II
Was ist der Unterschied zwischen propriozeptiven und extereozeptiven Sensoren? Nennen Sie jeweils Beispiele!
Was ist Odometrie?
Was ist ein LiDAR-Sensor?
Was sind weitere Sensoren autonomer Fahrzeuge? (Radar, Ultraschall, Kamera, GNSS, IMU)
## Kapitel 3
### Questions I
Was ist eine Standardform zur Beschreibung von Roboterkinematiken?  bzw.: Warum werden Roboter nicht beliebig/wahlfrei entworfen sondern mit bestimmten Einschränkungen?
Was ist der Unterschied zwischen Vorwärts- und inverser Kinematik?
Welche Arten von Rädern sind bei Robotern zu finden?
### Questions II
Wofür steht SLAM, was ist damit gemeint?
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