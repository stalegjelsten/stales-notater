---
{"dg-publish":true,"permalink":"/Kunnskap/Nettverksmaske/","title":"Nettverksmaske","tags":["ikt100","nettverk"]}
---

# Nettverksmaske

Størrelsen på det [[Kunnskap/LAN\|lokale nettverket]] (antall enheter) er bestemt av nettverksmasken. For eksempel vil nettverksmasken `/24` angi at 24 bits av [[Kunnskap/IP-adresse\|IP-adressen]] settes av til nettverks-IDen. En [[Kunnskap/IP-adresse#IPv4\|IPv4-adresse]] er 32 bits, slik at vi kun har 8 bits til å adresse enheter på nettverket. Det vil gi oss $2^8 =256$ mulige adresser, men adresse 192.168.1.0 er adressen til nettverket og adresse 192.168.1.255 er en broadcastadresse.
