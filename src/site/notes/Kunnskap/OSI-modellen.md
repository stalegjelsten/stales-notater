---
{"dg-publish":true,"permalink":"/Kunnskap/OSI-modellen/","title":"OSI-modellen","tags":["ikt100","nettverk"]}
---


# OSI-modellen
OSI-modellen (<abbr>Open Systems Interconnection</abbr>) er en modell av [[Kunnskap/Datanettverk\|nettverkssystemer]] som består av syv ulike lag, se tabellen.

| Lag | Navn               | Trafikk         | Adressering     | Eksempler                                              |
|:---:| ------------------ | --------------- | --------------- | ------------------------------------------------------ |
|  1  | Fysisk lag         | Bits            |                 | Ethernetkabler, fiberoptiske kabler, trådløse signaler |
|  2  | [[Kunnskap/Datalinklaget\|Datalinklaget]]  | Rammer          | [[Kunnskap/MAC-adresse\|MAC-adresse]] | Ethernet, Wi-Fi                                        |
|  3  | Nettverkslaget     | Datagrammer     | [[Kunnskap/IP-adresse\|IP-adresse]]  | IP-pakker                                              |
|  4  | Transportlaget     | Segmenter       |                 | [[Kunnskap/TCP\|TCP]], [[Kunnskap/UDP\|UDP]]                                       |
|  5  | Sesjonslaget       | Data            |                 | Initierer sesjonen med *motparten*                     |
|  6  | Presentasjonslaget | Data            |                 | Bestemmer formatering                                  |
|  7  | Applikasjonslaget  | Meldinger, Data |                 | [[Kunnskap/HTTP\|HTTP]]                                               |
