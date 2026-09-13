# Monitoring, Sicherheit und Verfügbarkeit

## Monitoring und Kapazität

Kennzahlen wie CPU, RAM, Speicher, Durchsatz, Latenz, Jitter, Paketverlust, Fehlerzähler und Prozesswerte nur im Kontext bewerten. Eine Baseline beschreibt den Normalzustand; Trends sind oft wichtiger als Einzelwerte.

Kapazitätsplanung: aktuellen Verbrauch messen → Wachstum bestimmen → Reserve festlegen → Engpass prognostizieren → Maßnahme und Kontrollpunkt planen. Antwortschema: Messwert → Bewertung → Risiko/Ursache → Maßnahme.

## Sicherheit

Schutzziele sind Vertraulichkeit, Integrität und Verfügbarkeit; je nach Fall auch Authentizität und Nachvollziehbarkeit. Least Privilege begrenzt Benutzer und Dienste auf erforderliche Rechte.

Firewallregeln anhand Quelle, Ziel, Protokoll, Port, Richtung und Verbindungszustand lesen. VLANs allein kontrollieren keine erlaubte Kommunikation; erst Routing- und Firewallregeln tun dies. Begründungen sollten das konkrete Risiko und verbesserte Schutzziel nennen.

Zertifikate an Gültigkeit, Hostname, Zertifizierungsstelle und Zertifikatskette prüfen. TLS/HTTPS und SSH schützen Transportwege. Technische Maßnahmen wie Segmentierung, MFA, Updates und Verschlüsselung brauchen organisatorische Ergänzungen wie Rollen, Freigaben, Schulung und Dokumentation.

## Redundanz und Wiederherstellung

Ein Single Point of Failure kann das Gesamtsystem stilllegen. Redundanz kann Komponenten oder Pfade doppeln, erhöht aber Kosten und Komplexität. Failover muss getestet werden.

RAID schützt je nach Level gegen Datenträgerausfälle oder erhöht Leistung, ist aber kein Backup. Ein Backup ist eine separate, wiederherstellbare Datenkopie. Die 3-2-1-Grundidee: drei Kopien, zwei Medientypen, eine externe/offline Kopie. Restore-Tests sind Pflicht.

- RPO: maximal tolerierbarer Datenverlust, als Zeitspanne
- RTO: maximal tolerierbare Wiederherstellungszeit
- USV: überbrückt Stromausfall kurzfristig und ermöglicht geordnetes Herunterfahren
