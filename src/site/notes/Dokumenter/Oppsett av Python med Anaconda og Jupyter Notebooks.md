---
{"dg-publish":true,"permalink":"/Dokumenter/Oppsett av Python med Anaconda og Jupyter Notebooks/","title":"Jupyter Notebooks"}
---



# Introduksjon

## Hvorfor bruke Jupyter Notebooks?

Det er to grunner til at dere lærer programmering på videregående:

1. Dere skal bli bedre til å tenke algoritmisk – altså at dere bryter ned kompliserte problemer til enklere problemer som kan løses i ulike steg
2. Dere skal bruke teknologi som gjør dere i stand til å løse problemer som er så kompliserte at de ikke kan løses uten hjelpemidler

Jupyter Notebooks er en type filer hvor du kan kombinere tekst, matematikk og programmering i samme fil. Det gjør at det blir enklere for deg å skrive ned forklaringer til programmene dine, og du kan lage en Notebook (notatblokk) til hvert tema vi programmerer. Istedenfor å sjekke 6 forskjellige filer med serielåneksempler, så kan du nå sjekke en fil hvor du både har tekst og eksempler.

Vi skal skrive Pythonkoden i programmet Visual Studio Code. Det gjør at datamaskinen automatisk fullfører navnene på funksjoner og på variabler, slik at du skriver mindre feil og får færre feilmeldinger.

> [!info] Hva er spesielt med Jupyter Notebooks?
> I motsetning til vanlige `.py`-filer kan Jupyter Notebooks blande _kode_, _tekstforklaringer_ og _resultater_ (for eksempel grafer og tabeller) i samme dokument.
> Dette gjør at du kan forklare hva koden gjør samtidig som du viser kjøringen av den.
>
> Dette er spesielt nyttig når du skal:
>
> - Dokumentere prosessen din steg for steg
> - Lære nye konsepter og ha forklaringer rett ved siden av koden
> - Lage rapporter der både teori, kode og resultater henger sammen
>
> Jupyter Notebook-filer har filendelsen `.ipynb`.

## Mappestruktur for programmering

![Foreslått mattestruktur for programmering](/img/user/_resources/onedrive-filstruktur-programmering.png)


Jeg anbefaler at du lager en egen mappe til programmeringen i matematikk. Du velger selv hvordan du gjør dette, men jeg vil anbefale at du har alle skolefilene dine i OneDrive-mappa på datamaskinen. Et eksempel på en fornuftig filstruktur er vist i figur 1.


# Installasjon av programvare

For å kunne bruke Jupyter Notebooks må vi installere to programmer: Anaconda og Visual Studio Code.

- Anaconda er en samling av Python og mange tilleggsprogrammer. Det er en stor pakke som egentlig er litt _overkill_ sammenlignet med hva vi trenger i videregående, men du trenger kun å installere Anaconda en gang.
- Visual Studio Code er programmet vi skriver koden vår i.

## Framgangsmåte for installasjon av programmer

- Åpne programmet `Terminal`. Du finner det ved å trykke på Windows-knappen <kbd>Windows</kbd> og skrive inn `Terminal`.
- Installer Anaconda ved å skrive inn nøyaktig denne kommandoen (det tar kjempelang tid).

   ```powershell
   winget install --source winget -e --id Anaconda.Anaconda3
   ```

   Dersom du får spørsmål om å godta vilkår så skriver du bokstaven `J` eller `Y` for å godta.

- Etter at Anaconda er ferdig installert, så installerer du Visual Studio Code med følgende kommando

   ```powershell
   winget install --source winget -e --id Microsoft.VisualStudioCode
   ```

# Oppsett av programvare

> [!info] Om Visual Studio Code
> Visual Studio Code er et koderedigeringsprogram som kan brukes til alle programmeringsspråk. Vi skal bruke det til å skrive Python-kode ved hjelp av en funksjon som heter Jupyter notebooks.

## Installere utvidelser i Visual Studio Code

Vi skal installere to utvidelser til Visual Studio Code for å kunne skrive Python-kode effektivt. Åpne først Visual Studio Code ved å åpne Start menyen (trykk på <kbd>Windows</kbd>-knappen) og skriv inn `Code`.

1. Åpne `Extensions` → Søk etter `Python` → Trykk på `Installer`-knappen. Se figur 2.
2. Åpne `Extensions` → Søk etter `Jupyter` → Trykk på `Installer`-knappen.
3. [**Frivillig:**]{#black} Åpne `Extensions` → Søk etter `Black Formatter` → Trykk på `Installer`-knappen.

**OBS!** Alle disse tre utvidelsene er utviklet av Microsoft. Pass på at de er merket med ☑ **Microsoft**.

![Installere utvidelser i Visual Studio Code](/img/user/_resources/utvidelser.png)

## Deaktivere Copilot

1. Åpne kommandopaletten ved å trykke knappene <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>P</kbd> (eller velg `View` → `Command Palette` fra verktøylinja i toppen av programvinduet).
2. Skriv inn `Copilot disable`.
3. Du vil nå se flere valg, velg linjen med `GitHub Copilot: Disable completions`

> [!warning] Deaktivere Copilot
> [Copilot](https://code.visualstudio.com/docs/copilot/getting-started) i Visual Studio Code er et kunstig intelligens-verktøy som hjelper oss å kode, blant annet ved at det foreslår hva vi bør skrive.
>
> Det er et fantastisk verktøy, men for at vi mennesker skal lære, så er vi nødt til å tenke. Synapsene i hjernen din vil bli sterkere dersom det er _du som finner løsningen_, enn hvis du godtar løsningen til noen andre. Det tar litt lengre tid å gjøre det selv, men vi er tross alt på skolen for å lære og utvikle oss, ikke for å skrive mest mulig Pythonkode.

## Oppstart av Visual Studio Code

1. Velg `File` → `Open Folder` og marker mappa til Python-programmene dine. Trykk på `Velg mappe`.
2. Åpne kommandopaletten ved å trykke knappene <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>P</kbd> (eller velg `View` → `Command Palette` fra verktøylinja i toppen av programvinduet).
3. Velg `Create: New Jupyter notebook`. Du har nå opprettet en Jupyter Notebook. Dette er en fil som kan inneholde flere bokser med Python-kode og flere bokser med tekst.
4. Du må velge en _kernel_ for å kunne kjøre Python-koden. Velg `Select Kernel` og `Python Environments…`, se figur 3. Deretter velger du `anaconda3`, se figur 4.

![`Select Kernel` og `Python Environments…`](/img/user/_resources/vscode-select-kernel.png)

![Velg kernelen som heter `anaconda3`](/img/user/_resources/vscode-select-kernel2.png)

# Bruk av Jupyter Notebooks

En Jupyter Notebook (heretter kaller vi dem bare notatblokker) består av én eller flere bokser med kode eller tekst.

1. Du legger til en ny boks med kode ved å trykke på `+ Code`, se figur 5.
2. Du legger til en ny boks med tekst ved å trykke på `+ Markdown`, se figur 5.

Ved siden av boksene så finnes det en liten avspillingsknapp ▷ som _kjører_ koden i boksen. Variabler som opprettes i en boks er også tilgjengelige i de andre boksene. På denne måten kan du fortsette et program over flere bokser om du ønsker. _Output_ fra en boks vises direkte under boksen.

![Opprett bokser og kjør kode](/img/user/_resources/notebook.png)

Legg gjerne merke til at notatblokken min _ikke_ er lagret enda. Det kan du se ved at filen heter `Untitled-1.ipynb`, samtidig som du ser en hvit sirkel ved siden av filnavnet.

> [!tip] 💾 Lagre ofte!
> Du er nødt til å lagre din Jupyter Notebook selv. Du kan lagre på to måter:
>
> 1. Tast hurtigtastene <kbd>Ctrl</kbd><kbd>S</kbd>.
> 2. Velg `File` → `Save` fra menylinja helt i øvre, venstre hjørne av vinduet.

# Bruk av notatblokker til Python

Etter at du har opprettet en ny kodeblokk med `+ Code`-knappen er du klar til å skrive Pythonkode. Gjør en test allerede nå ved å legge inn et enkelt Pythonprogram og trykk på ▷.

```python
a = 2
b = 3
c = a * b
print(c)
```

> [!tip] Hurtigtaster
> - Tast <kbd>Shift</kbd><kbd>Enter</kbd> for å kjøre koden i en boks istedenfor å trykke på ▷ knappen.
> - Tast <kbd>Alt</kbd><kbd>Shift</kbd><kbd>F</kbd> for å formatere koden pent (krever at du installerte [Black Formatter](#black))
> - Tast <kbd>Shift</kbd><kbd>L</kbd> for å vise linjenummere i koden din (det er spesielt nyttig når du skal tolke feilmeldinger)

## IntelliSense og hjelp uten internett

Når du skriver Pythonkode i Visual Studio Code, får du automatisk hjelp gjennom **IntelliSense**.
Dette gjør at programmet foreslår variabler, funksjoner og metoder mens du skriver.

Hvis du har importert mattefunksjoenen med `import math`, og du skriver `math.` så vil det komme opp en liste med alt som finnes i pakken `math`, som `sin`, `cos` og `sqrt`.
Hvis du holder musepekeren over en funksjon, får du ofte en kort forklaring på hva den gjør og hvilke argumenter den tar inn.

Dette er nyttig når du ikke husker alt utenat, eller når du ønsker å oppdage hvilke muligheter et bibliotek gir.

### Finne riktig funksjon

Ofte lurer man på: **"Hvilken funksjon skal jeg bruke?"**
- IntelliSense kan hjelpe deg å se hva som finnes i en pakke.
- Hvis du bare skriver `plt.` (fra `matplotlib.pyplot`) og trykker på <kbd>Tab</kbd>, får du opp en liste over alle funksjoner du kan bruke.
- Hvis du begynner å skrive deler av navnet, foreslår IntelliSense riktig funksjon, f.eks. `plt.plo` → `plt.plot()`.

Dette gjør det lettere å lære nye biblioteker.

### Hjelpefunksjoner i notatblokker

Selv uten internett kan du finne ut mye om hvordan funksjoner og pakker fungerer.

Hvis du skriver `?` etter navnet på en funksjon så får du opp en kort dokumentasjon av funksjonen. Til venstre har jeg satt spørsmålstegn etter `randint()`-funksjonen for å finne ut hvordan denne fungerer. Til høyre ser du svaret fra Jupyter Notebook.

<!-- two-column start left-width=36% -->

```python
import random
random.randint?
```

---

```text
Signature: random.randint(a, b)
Docstring:
Return random integer in range [a, b], including both end points.
```

<!-- two-column stop -->

## Feilsøking i notatblokker

> [!info] Hva er en debugger?
> En _debugger_ (engelsk for å fjerne [_bugs_](https://no.wikipedia.org/wiki/Programvarefeil)) er et feilsøkingsverktøy – det hjelper deg å finne feilene i programmet ditt. Feilsøkingsverktøyet er spesielt nyttig i de tilfellene hvor det ikke er noe åpenbart feil med programmet ditt, men du er usikker på om svarene riktige.

Feilsøkingsverktøyet (engelsk: _debuggeren_) i Visual Studio Code lar deg blant annet gå gjennom et Pythonprogram steg-for-steg. Du kan starte en enkel versjon av feilsøkingsverktøyet ved å markere en linje i koden din og taste <kbd>F10</kbd> (du må sikkert holde inn <kbd>Fn</kbd>-tasten samtidig). Fortsett å taste <kbd>F10</kbd> for å gå gjennom programmet ditt linje-for-linje. Du kan følge med på hvordan verdiene av variablene utvikler seg, slik som vist i figur 7.

> [!warning] 💾 Husk å lagre!
> Feilsøkingsverktøyet vil ikke fungere før du har lagret notatblokken din. <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>S</kbd>

### Bruke bruddpunkter til feilsøking

For å starte fullversjonen av feilsøkingsverktøyet må du først definere et bruddpunkt (engelsk: _break point_) i koden din, se figur 6. Dette gjøres ved å klikke i margen til venstre for kodeblokken. Veldig ofte ønsker vi å finne ut hva som skjer inni en løkke, da må du sette bruddpunktet på linja som starter løkka.

![Bruddpunkt på linje 5](/img/user/_resources/bruddpunkt.png)

Etter at bruddpunktet er satt så kan du starte feilsøkingsverktøyet ved å klikke på nedoverpilen (⌄) markert _Debug cell_ i figur 6, eller ved å trykke hurtigtasten <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>Enter</kbd>. Programmet kjører da helt fram til bruddpunktet, deretter stopper kjøringen av programmet, og du kan bruke feilsøkingsverktøyene.

### Bruk av feilsøkingsverktøyet

Når feilsøkeren har startet så ser du et bilde som vist i figur 7. Til venstre ser du de nåværende verdiene til alle variablene i programmet. I tillegg ser du verdiene av variablene i selve kodeblokken (se den grå teksten i linje 1–3). Figur 7 viser også feilsøkingsverktøyene i toppen av skjermen.

1. <kbd>F5</kbd> Bruk `Continue`-knappen (▶) for å kjøre programmet helt fram til bruddpunktet.
2. <kbd>F10</kbd> Bruk `Step Over`-knappen (↷) for å kjøre neste linje av programmet.
3. <kbd>Shift</kbd><kbd>F5</kbd> Bruk `Disconnect`-knappen (🔌) for å avslutte debuggingen.

<!-- two-column start left-width=52.5% -->

![Verktøyene i debuggeren](/img/user/_resources/debug-1.png){#fig:debug1}

---

![Variablenes verdier er synlige](/img/user/_resources/debug-3.png){#fig:debug2}

<!-- two-column stop -->

## Se verdien av alle variabler

Du kan se verdiene til _alle_ variablene i koden din uten å bruke `print()`-funksjonen. Trykk på `Jupyter Variables` i menylinja (knappen ligger til høyre for `+ Code` og `+ Markdown`).

## Kopiere kode til OneNote eller Word

Hvis du kopierer koden din (<kbd>Ctrl</kbd><kbd>C</kbd>) og limer inn i OneNote eller Word (<kbd>Ctrl</kbd><kbd>V</kbd>) så vil du se at fargeleggingen av koden din følger med.

<!-- pagebreak -->


# Skriv tekst og matematikk i notatblokka

Etter at du har opprettet en ny tekstblokk med `+ Markdown`-knappen er du klar til å skrive tekst. _Markdown_ er et tekstformat som bruker enkle symboler for å formatere tekst. Det kraftigste verktøyet for skolebruk er nok muligheten til å skrive matematikk.

## Enkel formatering i Markdown

```markdown
# Overskrift på nivå 1
### Overskrift på nivå 3
*Stjerner rundt teksten uthever teksten med kursiv*
**Doble stjerner uthever teksten med fet skrift**

En tom linje starter et nytt avsnitt.

- En punktliste starter med bindestrek
1. Nummererte lister begynner med tall og punktum
2. Matematikk på linje med teksten skrives som $x=2$
```

## Skrive matematikk i Markdown

Markdown i notatblokker har innebygd støtte for [LaTeX](https://en.wikipedia.org/wiki/LaTeX)-kode til matematikk. Dette er den vanligste måten å skrive matematikk internasjonalt. Det tar tid å lære seg alle funksjonene i LaTeX, men du kommer fort i gang og lærer deg det viktigste! Du kan også bruke LaTeX-kode til å skrive formler i Microsoft Word.

Til venstre så ser du koden du kan skrive i Markdownblokkene, og til høyre ser du hvordan resultatet blir dersom du velger å kjøre Markdownblokken ved å trykke på ▷. Legg merke til at vi bruker doble dollartegn (`$$x=2$$`) for å skrive matematikk som står alene på en linje og enkle dollartegn (`$x=2$`) for å skrive matematikk som står på samme linje som teksten.

<!-- two-column start left-width=60% -->

````markdown
$f(x) = 2x^3$
Vi vet at $a_n = a_1 + (n-1) \cdot d$, derfor…

$ x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} $

$\sum_{i=1}^n 2^{i-1} = 1+2+4+8+\dots$
````

---

$$f(x) = 2x^3$$

Vi vet at $a_n=a_1+(n-1) \cdot d$, derfor…

$$ x= \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$
$$ \sum_{i=1}^n 2^{i-1} = 1 + 2 + 4 +8 +\dots $$

<!-- two-column stop -->

For å vise ferdig formatert tekst så kan du trykke på ✓ eller hurtigtastene <kbd>Shift</kbd><kbd>Enter</kbd> eller <kbd>Esc</kbd>, se figur 8.

![Markdownkode i redigeringsmodus og visningsmodus](/img/user/_resources/vis-markdown.png)

De viktigste matematikkfunksjonene i LaTeX finner du på [denne nettsiden](https://www.rpubs.com/aaaaaa1234sta/1197405). En oversikt over nesten alle matematikkfunksjonene finner du hos [LaTeX på Wikibooks](https://en.wikibooks.org/wiki/LaTeX/Mathematics).
