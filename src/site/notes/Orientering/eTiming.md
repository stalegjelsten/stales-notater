---
{"dg-publish":true,"permalink":"/Orientering/eTiming/","title":"eTiming","tags":["etiming"]}
---


# eTiming
eTiming er et tidtakingsprogram for Windows som kan brukes [[Orientering/eTiming til Agderkarusell\|under løpet]] eller til å [[Orientering/eTiming med spooling av resultater\|spoole]] resultater i etterkant.

## Installasjon

### Installasjon av eTiming
EQ Timing forklarer installasjon av programmet på denne siden: <https://eqtiming.freshdesk.com/nb-NO/support/solutions/articles/19000131413-etiming-4-2022-installasjon.html>

Informasjonen på nettsiden fra EQ Timing som står fra *SQL Server* og nedover er ikke relevant for bruk på små løp (treninger/nærløp/kretsløp). Denne informasjonen er mest relevant dersom man ønsker å bruke flere datamaskiner i nettverk til å dele på tidtakeroppgavene.

Per 2023-09-03 så ser det ikke ut til at man får lastet ned nyeste versjon av programvaren her. Se instruksjonene under [[Orientering/eTiming#Oppdatering av eTiming\|#Oppdatering av eTiming]] for å oppdatere til siste versjon.

>[!note] Registrere lisensnøkkel
>eTiming blir installert som demoprogramvare. Da har du kun mulighet til å registrere 100 løpere på arrangementet.
>
> For å registrere flere løpere må du legge inn en lisensnøkkel og klubbnavn under `Help → About → Lisens`.
>
>Restart eTiming for at lisensen skal bli gyldig.

### Installasjon av MTR drivere
For å lese av tider fra EMIT-brikkene bruker vi en MTR4-brikkeavleser. For å koble denne til PCen og til eTiming så trenger du å installere en driver. Last ned driveren og les mer hos [emit.no](https://emit.no/support-base/emit-mini-time-recorder-mtr4/)

## Oppdatering av eTiming
eTiming oppdateres relativt ofte, og det er lurt å benytte nyeste versjon til løp (men ta gjerne backup av gjeldende versjon før du oppdaterer). Eldre versjoner kan f.eks. ha problemer med tilkobling til Eventor, men det er viktig å være oppmerksom på at nye versjoner også kan inneholde bugs.

For å oppdatere eTiming gjør du følgende:
1. Avslutt eTiming (hvis det kjører)
2. Gå til eTiming sin programkatalog (ofte vil det være `C:\Program files (x86)\eTiming\`)
3. Lag en backup av`etiming.exe` ved å gi den et nytt navn, f.eks `etiming 922.exe` for versjon 922.
4. Gå til [https://eqtiming.freshdesk.com/nb-NO/support/solutions/articles/19000136125-etiming-programoppdatering](https://eqtiming.freshdesk.com/nb-NO/support/solutions/articles/19000136125-etiming-programoppdatering)
5. Last ned `.zip`-fila i bunnen av artikkelen
6. Åpne `.zip`-fila og kopier `etiming.exe` filen over til eTiming som programkatalog (ofte vil det være `C:\Program files (x86)\eTiming\`)
7. De resterende filene i `.zip`-fila er ikke nødvendige for oppdatering.

## Problemer med eTiming

### Begrensninger
- Liveresultater fungerer mot Liveres.live, men kan ikke starte under Win xp 32 bit
- Automatisk gjenkjenning av gafling fungerer ikke.

### Bugs
- Statusene Fullført og Fullført i eTiming gir begge «utenfor konkurranse» i Eventor. Det finnes en egen status «utenfor konkurranse» i eTiming også!
	- Hvis man ønsker å få *Fullført* som status i Eventor kan dette løses manuelt i iofres.xml ved å søk/erstatt NotCompeting med Finished. Eks: `gsed -i 's/NotCompeting/Finished/' iofres.xml`

## Related
- [[Orientering/etiming kurs\|etiming kurs]]
- [[Orientering/Importere påmeldinger fra Excel i eTiming\|Importere påmeldinger fra Excel i eTiming]]
- [[Orientering/eTiming\|eTiming]]
- [[Orientering/eTiming til sommercup\|eTiming til sommercup]]
- [[Orientering/eTiming til Agderkarusell\|eTiming til Agderkarusell]]
- [[Orientering/eTiming med gafling\|eTiming med gafling]]
- [[Orientering/eTiming database\|eTiming database]]
- [[Orientering/LiveRes for etiming\|LiveRes for etiming]]

{ .block-language-dataview}
