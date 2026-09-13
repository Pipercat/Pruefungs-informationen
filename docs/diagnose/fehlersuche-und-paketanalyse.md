# Diagnose, Fehlersuche und Paketanalyse

## Methodisches Vorgehen

1. Fehlerbild, Zeitpunkt, Umfang und Randbedingungen aufnehmen.
2. Sollzustand und bekannte Änderungen klären.
3. Istzustand mit Messwerten, Konfiguration und Logs erfassen.
4. Symptome von Ursachen trennen und Hypothesen priorisieren.
5. Mit gezielten, möglichst wenig invasiven Tests eingrenzen.
6. Ursache bestätigen, Maßnahme durchführen und Wirkung kontrollieren.
7. Änderung, Ergebnis und gegebenenfalls Rückfallplan dokumentieren.

Methoden: Bottom-up, Top-down, Divide and Conquer, Known-Good-Vergleich sowie Fehlerbaum. Änderungen auf Verdacht sind keine systematische Diagnose.

## Werkzeuge

| Werkzeug | Prüft vor allem |
| --- | --- |
| `ping` | IP-/ICMP-Erreichbarkeit und Laufzeit |
| `traceroute` / `tracert` | Router-Hops und Abbruchstelle |
| `ipconfig` / `ip` | Adresse, Präfix, Gateway, Interface |
| `arp` / `ip neigh` | lokale Nachbarschaftszuordnung |
| `route` / `ip route` | Routingtabelle und Standardroute |
| `nslookup` / `dig` | DNS-Auflösung und antwortender Server |
| `netstat` / `ss` | Listener und Verbindungen |
| Logs | Ereignisse, Zeitstempel, Fehlercodes und Kontext |
| Wireshark | tatsächlicher Protokollablauf im Netz |

Zu jedem Werkzeug gehören erwartetes Ergebnis und Interpretation.

## Typische Mitschnittbefunde

- wiederholte SYNs ohne Antwort: Host, Firewall, Routing oder Rückweg prüfen
- sofortiges RST: Host erreichbar, Port/Dienst nicht offen
- DNS-Anfrage ohne Antwort: DNS-Server oder Pfad gestört
- wiederholtes DHCP Discover ohne Offer: DHCP nicht erreichbar oder antwortet nicht
- ARP ohne Reply: Ziel nicht im Layer-2-Segment erreichbar, VLAN oder Adresse prüfen

## Sinnvolle Diagnosekette

Link/Interface → IP-Konfiguration → lokaler Nachbar → Gateway → Route und Rückroute → DNS → Transportport → Anwendung → detaillierter Mitschnitt und korrelierte Logs.

Bei OT-/Prozessdaten zusätzlich Zeitstempel, Grenzwerte, Sensor-/Aktorzustände, Zykluszeiten und Kommunikationszustände abgleichen.
