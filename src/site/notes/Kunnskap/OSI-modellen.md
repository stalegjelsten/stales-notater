---
{"dg-publish":true,"permalink":"/Kunnskap/OSI-modellen/","title":"OSI-modellen","tags":["ikt100","nettverk"]}
---


# OSI-modellen
OSI-modellen (<abbr>Open Systems Interconnection</abbr>) er en modell av [[Kunnskap/Nettverk\|nettverkssystemer]] som består av syv ulike lag


| Lag | Navn              | Trafikk | Adressering     | Eksempler                                              |
| :-: | ----------------- | ------- | --------------- | ------------------------------------------------------ |
|  1  | Fysisk lag        |         |                 | Ethernetkabler, fiberoptiske kabler, trådløse signaler |
|  2  | [[Kunnskap/Datalinklaget\|Datalinklaget]] | Rammer  | [[Kunnskap/MAC-adresse\|MAC-adresse]] | Ethernet, Wi-Fi                                        |
|  3  |                   |         |                 |                                                        |


1. Fysisk lag (L1). Ethernetkabler, fiberoptiske kabler, trådløse signaler.
2. [[Kunnskap/Datalinklaget\|Datalinklaget]] (L2) er mellom enheter i samme [[Kunnskap/LAN\|lokale nettverk]]. Ethernet, Wi-Fi. Datatrafikken sendes som rammer og man bruker [[Kunnskap/MAC-adresse\|MAC-adresser]] som adresse.
3. Nettverkslaget (L3). [[Ruting\|Ruting]] av datapakker mellom ulike nettverk. Datatrafikken sendes som pakker til og man bruker [[Kunnskap/IP-adresse\|IP-adresser]] som adresser.
4. Transportlaget (L4). Transport av data mellom to endepunkter. [[TCP\|TCP]] og [[UDP\|UDP]]
5. Sesjonslaget (L5)
6. Presentasjonslaget (L6).
7. Appllikasjonslaget (L7). Dette er laget brukeren interagerer med. [[Kunnskap/HTTP\|HTTP]]
