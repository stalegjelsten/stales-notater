---
{"dg-publish":true,"permalink":"/Orientering/eTiming/","title":"eTiming","tags":["etiming"]}
---


# eTiming
eTiming er et tidtakingsprogram for Windows som kan brukes til [[Orientering/eTiming med spooling av resultater\|enkle løp med spooling]] eller til full tidtaking.

## Installasjon

### Installasjon av eTiming
EQ Timing forklarer installasjon av programmet på denne siden: <https://eqtiming.freshdesk.com/nb-NO/support/solutions/articles/19000131413-etiming-4-2022-installasjon.>

Informasjonen på nettsiden som står fra *SQL Server* og nedover er ikke relevant for bruk på små løp (treninger/nærløp/kretsløp). Denne informasjonen er mest relevant dersom man ønsker å bruke flere datamaskiner i nettverk til å dele på tidtakeroppgavene.

Per 2023-09-03 så ser det ikke ut til at man får lastet ned nyeste versjon av programvaren her. Se instruksjonene under [[Orientering/eTiming#Oppdatering av eTiming\|eTiming#Oppdatering av eTiming]] for å oppdatere til siste versjon.

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

| file.inlinks                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <ul><li>[[Orientering/etiming kurs.md\\|etiming kurs]]</li><li>[[Orientering/eTiming.md\\|eTiming]]</li><li>[[Orientering/eTiming til sommercup.md\\|eTiming til sommercup]]</li><li>[[Orientering/eTiming til nærløp.md\\|eTiming til nærløp]]</li><li>[[Orientering/eTiming til Agderkarusell.md\\|eTiming til Agderkarusell]]</li><li>[[Orientering/eTiming med spooling av resultater.md\\|eTiming med spooling av resultater]]</li><li>[[Orientering/eTiming med gafling.md\\|eTiming med gafling]]</li><li>[[Orientering/eTiming database.md\\|eTiming database]]</li><li>[[Orientering/LiveRes for etiming.md\\|LiveRes for etiming]]</li></ul> |

{ .block-language-dataview}

[[Orientering/eTiming med gafling\|eTiming med gafling]]

### Begrensninger
- Liveresultater fungerer mot Liveres.live, men kan ikke starte under Win xp 32 bit
- Automatisk gjenkjenning av gafling fungerer ikke.

### Bugs
- Statusene Fullført og Fullført i eTiming gir begge «utenfor konkurranse» i Eventor. Det finnes en egen status «utenfor konkurranse» i eTiming også!
	- Hvis man ønsker å få *Fullført* som status i Eventor kan dette løses manuelt i iofres.xml ved å søk/erstatt NotCompeting med Finished. Eks: `gsed -i 's/NotCompeting/Finished/' iofres.xml`
