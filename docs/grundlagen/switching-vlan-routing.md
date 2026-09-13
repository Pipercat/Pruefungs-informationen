# Switching, VLAN und Routing

## VLAN und Ports

Ein VLAN bildet eine logisch getrennte Broadcast-Domäne auf gemeinsamer Hardware. Ein Access-/Untagged-Port gehört gewöhnlich zu einem VLAN. Ein Tagged-Port/Trunk transportiert mehrere VLANs per IEEE 802.1Q, etwa zwischen Switches, Firewall und Access Point.

Die PVID ordnet ungetaggte eingehende Frames einem VLAN zu. Typische Fehler sind unterschiedliche Tagged/Untagged-Konfigurationen, falsche PVID, ein auf dem Trunk fehlendes VLAN oder ein Endgerät im falschen VLAN.

Layer-2-Schleifen können Broadcast-Stürme auslösen. STP erzeugt eine schleifenfreie logische Topologie, indem es redundante Pfade kontrolliert blockiert.

## Routing

Liegt das Ziel im eigenen Präfix, kommuniziert ein Host direkt auf Layer 2. Andernfalls sendet er an das lokal erreichbare Standardgateway. Router verwenden die spezifischste passende Route (Longest Prefix Match).

- IPv4-Standardroute: `0.0.0.0/0`
- IPv6-Standardroute: `::/0`
- Route: Zielnetz, Präfix, Next Hop/Interface, ggf. Metrik

Jedes VLAN besitzt üblicherweise ein eigenes IP-Subnetz. Kommunikation zwischen VLANs benötigt einen Router, eine Firewall oder einen Layer-3-Switch. Dabei auch Firewallregeln und Rückroute prüfen.

## Merksätze

- VLAN trennt auf Layer 2; Inter-VLAN-Kommunikation braucht Layer 3.
- Bridging verbindet Segmente derselben Broadcast-Domäne; Routing verbindet IP-Netze.
- Ein erreichbares Gateway beweist weder die Route zum Ziel noch den funktionierenden Rückweg.
