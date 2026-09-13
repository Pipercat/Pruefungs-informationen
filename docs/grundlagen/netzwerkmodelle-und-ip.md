# Netzwerkmodelle, Ethernet und IP

## OSI- und TCP/IP-Modell

Das OSI-Modell unterstützt Kommunikation und Fehlersuche:

1. Bitübertragung: Kabel, Stecker, Signale, Funk
2. Sicherung: Ethernet, MAC, Frames, Switches, VLANs
3. Vermittlung: IPv4/IPv6, Routing, ICMP
4. Transport: TCP, UDP und Ports
5. Sitzung bis Anwendung: anwendungsnahe Kommunikation und Datenformate

Das TCP/IP-Modell fasst dies zu Netzzugang, Internet, Transport und Anwendung zusammen. Kapselung: Anwendungsdaten → Segment/Datagramm → IP-Paket → Ethernet-Frame → Bits.

## Ethernet und MAC

Ein Switch lernt aus der Quell-MAC, an welchem Port ein Gerät erreichbar ist. Bekannte Ziel-MACs werden gezielt weitergeleitet, unbekannte Ziele geflutet. Broadcasts erreichen alle Teilnehmer derselben Broadcast-Domäne; Multicast nur eine definierte Gruppe.

## IPv4 und Subnetting

Eine IPv4-Adresse besitzt 32 Bit. Das Präfix trennt Netz- und Hostanteil. Beispiel `192.168.10.25/24`: Netz `192.168.10.0`, Broadcast `192.168.10.255`, Hosts `.1` bis `.254`.

Private Bereiche: `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`. Eine Adresse aus `169.254.0.0/16` weist häufig auf fehlgeschlagenes DHCP hin.

Klassisch gilt: nutzbare Hosts = `2^Hostbits - 2`. Häufige Größen: `/25` 126, `/26` 62, `/27` 30, `/28` 14, `/29` 6, `/30` 2 Hosts. Bei VLSM zuerst das größte benötigte Netz vergeben.

Immer Netzadresse, Präfix, Hostbereich und Broadcast notieren. Prüfen, ob Gateway und Host im selben lokalen Subnetz liegen.

## IPv6

IPv6 besitzt 128 Bit. Führende Nullen einer Gruppe dürfen entfallen; genau eine zusammenhängende Nullfolge darf durch `::` ersetzt werden.

- Link Local: `fe80::/10`, nur im lokalen Segment
- Global Unicast: öffentlich routbar
- Multicast: ersetzt klassische Broadcasts
- typisches LAN-Präfix: `/64`

SLAAC nutzt Router Advertisements zur Konfiguration. Neighbor Discovery (NDP) basiert auf ICMPv6 und ersetzt funktional ARP. DHCPv6 kann ergänzende Angaben oder Adressen liefern.
