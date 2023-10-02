---
{"dg-publish":true,"permalink":"/Kunnskap/Server/","title":"Server","tags":["it1"]}
---


# Server
En server (norsk: tjener) er en datamaskin er en datamaskin som tilbyr (eller serverer) tjenester til brukere (også kalt klienter).

## Eksempel med webserver
La oss tenke oss følgende situasjon: Lise ønsker å lese forsiden til NRK på telefonen sin. Da vil følgende steg skje (litt forenklet)
- Lise taster inn [[Kunnskap/URL\|nettadressen]] <https://nrk.no> og trykker ok
- Nettleseren i telefonen vil bruke et [[DNS\|DNS]]-register for å finne ut hvilken [[IP-adresse\|IP-adresse]] som hører til <https://nrk.no>
- Nettleseren vil sende en forespørsel (engelsk: request) over protokollen `http` eller `https` om å bli servert nettsiden `index.html` fra NRK
- Webserveren mottar forespørselen og behandler den (det vil si at den finner fram fila i filsystemet og sender et svar på forespørselen)
- Nettsiden `index.html` blir sendt tilbake til Lise via `https`
- Nettleseren tolker `index.html` og viser innholdet på telefonskjermen

Da vil nettleseren i telefonen kommunisere med serveren som står bak [[Kunnskap/URL\|URLen]] og be om serveren skal sende `index.html` fila til nettleseren.
