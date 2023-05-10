---
{"dg-publish":true,"permalink":"/Orientering/eTiming/","title":"eTiming","tags":[null]}
---


# eTiming
eTiming kan brukes til [[Orientering/eTiming til enkle sommercup\|enkle løp med spooling]] eller til full tidtaking.

| file.inlinks                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <ul><li>[[Orientering/eTiming med gafling.md\\|eTiming med gafling]]</li><li>[[Orientering/eTiming til nærløp.md\\|eTiming til nærløp]]</li><li>[[Orientering/etiming kurs.md\\|etiming kurs]]</li><li>[[Orientering/eTiming til enkle sommercup.md\\|eTiming til enkle sommercup]]</li><li>[[Orientering/eTiming database.md\\|eTiming database]]</li><li>[[Orientering/eTiming til Agderkarusell.md\\|eTiming til Agderkarusell]]</li><li>[[Orientering/LiveRes for etiming.md\\|LiveRes for etiming]]</li></ul> |

{ .block-language-dataview}

[[Orientering/eTiming med gafling\|eTiming med gafling]]

### Begrensninger
- Liveresultater fungerer mot Liveres.live, men kan ikke starte under Win xp 32 bit
- Automatisk gjenkjenning av gafling fungerer ikke.
- Helt uforståelig kobling til kontingentnivåer fra Eventor. Hver klasse må ha eget kontingentnivå

### Bugs
- Statusene Fullført og Fullført i eTiming gir begge «utenfor konkurranse» i Eventor. Det finnes en egen status «utenfor konkurranse» i eTiming også!
	- Hvis man ønsker å få *Fullført* som status i Eventor kan dette løses manuelt i iofres.xml ved å søk/erstatt NotCompeting med Finished. Eks: `gsed -i 's/NotCompeting/Finished/' iofres.xml`
