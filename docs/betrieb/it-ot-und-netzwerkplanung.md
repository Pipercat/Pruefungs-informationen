# IT/OT und Netzwerkplanung

## Heterogene Systeme

Heterogene Systeme verbinden unterschiedliche Geräte, Hersteller, Betriebssysteme, Protokolle und Datenformate, etwa SPS, Sensor, Edge-Gateway, MQTT-Broker, Datenbank sowie Windows- und Linux-Systeme.

- Sensor: erfasst einen Zustand.
- Aktor: beeinflusst einen Prozess; sichere Zustände und Freigabelogik beachten.
- Gateway: verbindet Netze oder Protokolle und kann übersetzen, filtern oder puffern.
- Edge-Gerät: verarbeitet nahe an der Quelle; reduziert Latenz und Bandbreite und kann lokale Funktion bei Cloud-Ausfall erhalten.

## IT und OT

IT fokussiert typischerweise Daten, Benutzer und Anwendungen. OT steuert physische Prozesse; Verfügbarkeit, determinierbares Verhalten, Latenz und sichere Betriebszustände sind oft besonders kritisch. Ein typischer Datenfluss lautet:

Sensor/Aktor → Steuerung → Edge/Gateway → Server/Leitsystem → Cloud/Analyse.

## Planungsfragen

- Welche Geräte müssen in welche Richtung kommunizieren?
- Welche Datenmengen, Latenzen und Verfügbarkeiten werden benötigt?
- Welche Protokolle, Schnittstellen und Datenformate sind kompatibel?
- Welche IP-Netze, VLANs, Gateways, Routen und Firewallregeln sind nötig?
- Was geschieht bei Verbindungs-, Komponenten- oder Stromausfall?
- Wie werden Betrieb, Updates, Monitoring und Verantwortlichkeiten geregelt?

## Ergebnisdokumentation

Eine belastbare Planung enthält physische und logische Topologie, IP-/VLAN-Plan, Datenflüsse, Schnittstellen, Sicherheitsgrenzen, Verantwortlichkeiten, Test- und Abnahmekriterien.
