# Dienste, Transportprotokolle und APIs

## TCP, UDP und Ports

TCP ist verbindungsorientiert, geordnet und zuverlässig. Der Aufbau erfolgt mit `SYN → SYN-ACK → ACK`. Wiederholte SYNs ohne Antwort deuten unter anderem auf Routing, Firewall oder einen ausgefallenen Host; ein sofortiges RST meist auf einen erreichbaren Host ohne offenen Dienst. UDP ist verbindungslos und besitzt keine eingebaute Zustellgarantie.

Ports adressieren Dienste. Prüfungsrelevante Beispiele: SSH 22, DNS 53, DHCPv4 67/68, HTTP 80, HTTPS 443 und MQTT 1883 (unverschlüsselt). Ein erfolgreicher Ping bestätigt nur ICMP-Erreichbarkeit, nicht die Anwendung.

## Basisdienste

### DHCP

DORA: Discover → Offer → Request → Acknowledge. Fehlerbilder sind fehlende Angebote, erschöpfte Pools oder falsche Gateway-/DNS-Optionen. Reservierungen verbinden zentrale Verwaltung mit stabiler Adresszuweisung.

### DNS

DNS löst Namen auf. A verweist auf IPv4, AAAA auf IPv6 und CNAME auf einen anderen Namen. Funktioniert der Zugriff per IP, aber nicht per Namen, DNS mit `nslookup` oder `dig` separat prüfen.

### ARP, ICMP und NAT/PAT

ARP ordnet IPv4-Adressen lokalen MAC-Adressen zu. Für entfernte Ziele wird die MAC des Gateways benötigt. ICMP transportiert Diagnose- und Fehlermeldungen. NAT übersetzt Adressen; PAT unterscheidet mehrere Verbindungen zusätzlich über Ports. NAT ist keine vollständige Sicherheitsmaßnahme.

## HTTP(S), REST und JSON

HTTP arbeitet als Anfrage/Antwort-Protokoll; HTTPS schützt die Verbindung mit TLS. Methoden: GET lesen, POST anlegen/anstoßen, PUT vollständig ersetzen, PATCH teilweise ändern, DELETE löschen. Statusklassen: 2xx Erfolg, 3xx Umleitung, 4xx Anfrage-/Clientfehler, 5xx Serverfehler.

REST modelliert Ressourcen über Endpunkte. JSON enthält Objekte, Arrays und Schlüssel-Wert-Paare. Fehlerquellen: falscher Endpunkt, Methode, Port, Feldname oder Datentyp; fehlende Authentifizierung; inkompatible API-Version; DNS-, TLS- oder Netzwerkfehler.

Authentifizierung klärt „Wer bist du?“, Autorisierung „Was darfst du?“. Geheimnisse wie API-Keys und Tokens nie in Dokumentation oder Repository übernehmen.

## SSH und MQTT

SSH bietet verschlüsselte Fernadministration. MQTT arbeitet nach Publish/Subscribe: Publisher senden über einen Broker an Topics, Subscriber abonnieren Topics. Das entkoppelt Geräte in IoT-/OT-Systemen.
