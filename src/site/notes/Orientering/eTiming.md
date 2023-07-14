---
{"dg-publish":true,"permalink":"/Orientering/eTiming/","title":"eTiming","tags":[null]}
---


# eTiming
eTiming kan brukes til [[Orientering/eTiming med spooling av resultater\|enkle løp med spooling]] eller til full tidtaking.

| file.inlinks                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <ul><li>[[Orientering/eTiming med spooling av resultater.md\\|eTiming med spooling av resultater]]</li><li>[[Orientering/eTiming til Agderkarusell.md\\|eTiming til Agderkarusell]]</li><li>[[eTiming database(1).md\\|eTiming database(1)]]</li><li>[[Orientering/eTiming til sommercup.md\\|eTiming til sommercup]]</li><li>[[Orientering/LiveRes for etiming.md\\|LiveRes for etiming]]</li><li>[[Orientering/etiming kurs.md\\|etiming kurs]]</li><li>[[Orientering/eTiming til nærløp.md\\|eTiming til nærløp]]</li><li>[[Orientering/eTiming med gafling.md\\|eTiming med gafling]]</li></ul> |

{ .block-language-dataview}

[[Orientering/eTiming med gafling\|eTiming med gafling]]

### Begrensninger
- Liveresultater fungerer mot Liveres.live, men kan ikke starte under Win xp 32 bit
- Automatisk gjenkjenning av gafling fungerer ikke.
- Helt uforståelig kobling til kontingentnivåer fra Eventor. Hver klasse må ha eget kontingentnivå

### Bugs
- Statusene Fullført og Fullført i eTiming gir begge «utenfor konkurranse» i Eventor. Det finnes en egen status «utenfor konkurranse» i eTiming også!
	- Hvis man ønsker å få *Fullført* som status i Eventor kan dette løses manuelt i iofres.xml ved å søk/erstatt NotCompeting med Finished. Eks: `gsed -i 's/NotCompeting/Finished/' iofres.xml`
