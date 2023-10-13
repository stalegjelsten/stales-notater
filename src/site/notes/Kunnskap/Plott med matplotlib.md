---
{"dg-publish":true,"permalink":"/Kunnskap/Plott med matplotlib/","title":"Plott med matplotlib","tags":["python","it","uferdig"]}
---


# Plott med matplotlib
`matplotlib` er et bibliotek til [[Python\|Python]] som gjør det mulig å lage grafer og plott. Matplotlib er laget slik at det skal være enkelt for brukere av `MATLAB` til å gå over til Python. Det gjør at Matplotlib føles litt mindre pythonsk enn mange andre pythonbiblioteker.

## Installasjon
Prøv å importere Matplotlib med følgende kode

```python
import matplotlib.pyplot as plt
```

Hvis ikke Matplotlib er installert på datamaskinen så vil du få en feilmelding med `No module found`. 

Du kan installere Matplotlib i gjennom [Mu](https://codewith.mu) ved å gå til `Innstillinger` → `Third party packages` og skrive inn `matplotlib` på en linje i vinduet før du trykker `OK`.

Bruker du en annen tekstbehandler så installerer du Matplotlib på samme måte som du installerer andre pakker – for eksempel med `pip install matplotlib` eller `conda install matplotlib`

## Bruk matplotlib til å lage graf

Det finnes flere måter å opprette et plott på. Den enkleste moderne måten å gjøre dette er ved hjelp av `subplots`.

```python
import matplotlib.pyplot as plt
fig, ax = plt.subplots()
```

Nå vil variabelen `fig` være tilordnet et `Figure`-objekt, mens `ax` er tilordnet et koordinatsystemobjekt. 
- Vi kan bruke metoder på `fig` for å endre på egenskaper for hele figuren. `fig.set_size_inches(6,4)` vil gjøre figuren 6 tommer bred og 4 tommer høy. Det er spesielt nyttig å endre på hele figuren dersom vi har [[Kunnskap/Plott med matplotlib#Lag flere subplots i samme figur\|flere enn ett plott i figuren]].

### Plott data med ax.plot()
Vi ønsker å vise noen data i plottet vårt. Matplotlib har mange ulike typer diagrammer og grafer innebygd. Den vanligste graftypen er linjediagrammet som er tilgjengelig med `ax.plot()`. Metoden trenger som et minimum argumentene `x` og `y`. Dette skal være to lister eller arrays med data. Listene må være like lange.

```python
import matplotlib.pyplot as plt
import numpy as np
fig, ax = plt.subplots()
x = np.linspace(0,3,100)
y1 = x**2
y2 = 2*x

ax.plot(x, y1, c="blue", label="$x^2$")
ax.plot(x, y2, c="red", linestyle="dashed", label="$2x$")
ax.legend()
ax.set_title("$x^2$ og $2x$")
fig.show()
```

<svg xmlns:xlink="http://www.w3.org/1999/xlink" width="460.8pt" height="345.6pt" viewBox="0 0 460.8 345.6" xmlns="http://www.w3.org/2000/svg" version="1.1">
 <metadata>
  <rdf:RDF xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:cc="http://creativecommons.org/ns#" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
   <cc:Work>
    <dc:type rdf:resource="http://purl.org/dc/dcmitype/StillImage"/>
    <dc:date>2023-10-13T21:31:51.922222</dc:date>
    <dc:format>image/svg+xml</dc:format>
    <dc:creator>
     <cc:Agent>
      <dc:title>Matplotlib v3.6.3, https://matplotlib.org/</dc:title>
     </cc:Agent>
    </dc:creator>
   </cc:Work>
  </rdf:RDF>
 </metadata>
 <defs>
  <style type="text/css">*{stroke-linejoin: round; stroke-linecap: butt}</style>
 </defs>
 <g id="figure_1">
  <g id="patch_1">
   <path d="M 0 345.6 
L 460.8 345.6 
L 460.8 0 
L 0 0 
z
" style="fill: #ffffff"/>
  </g>
  <g id="axes_1">
   <g id="patch_2">
    <path d="M 57.6 307.584 
L 414.72 307.584 
L 414.72 41.472 
L 57.6 41.472 
z
" style="fill: #ffffff"/>
   </g>
   <g id="matplotlib.axis_1">
    <g id="xtick_1">
     <g id="line2d_1">
      <defs>
       <path id="mdde9edc3cd" d="M 0 0 
L 0 3.5 
" style="stroke: #000000; stroke-width: 0.8"/>
      </defs>
      <g>
       <use xlink:href="#mdde9edc3cd" x="73.832727" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_1">
      <!-- 0.0 -->
      <g transform="translate(65.881165 322.182437) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-30" d="M 2034 4250 
Q 1547 4250 1301 3770 
Q 1056 3291 1056 2328 
Q 1056 1369 1301 889 
Q 1547 409 2034 409 
Q 2525 409 2770 889 
Q 3016 1369 3016 2328 
Q 3016 3291 2770 3770 
Q 2525 4250 2034 4250 
z
M 2034 4750 
Q 2819 4750 3233 4129 
Q 3647 3509 3647 2328 
Q 3647 1150 3233 529 
Q 2819 -91 2034 -91 
Q 1250 -91 836 529 
Q 422 1150 422 2328 
Q 422 3509 836 4129 
Q 1250 4750 2034 4750 
z
" transform="scale(0.015625)"/>
        <path id="DejaVuSans-2e" d="M 684 794 
L 1344 794 
L 1344 0 
L 684 0 
L 684 794 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-30"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-30" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_2">
     <g id="line2d_2">
      <g>
       <use xlink:href="#mdde9edc3cd" x="127.941818" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_2">
      <!-- 0.5 -->
      <g transform="translate(119.990256 322.182437) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-35" d="M 691 4666 
L 3169 4666 
L 3169 4134 
L 1269 4134 
L 1269 2991 
Q 1406 3038 1543 3061 
Q 1681 3084 1819 3084 
Q 2600 3084 3056 2656 
Q 3513 2228 3513 1497 
Q 3513 744 3044 326 
Q 2575 -91 1722 -91 
Q 1428 -91 1123 -41 
Q 819 9 494 109 
L 494 744 
Q 775 591 1075 516 
Q 1375 441 1709 441 
Q 2250 441 2565 725 
Q 2881 1009 2881 1497 
Q 2881 1984 2565 2268 
Q 2250 2553 1709 2553 
Q 1456 2553 1204 2497 
Q 953 2441 691 2322 
L 691 4666 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-30"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-35" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_3">
     <g id="line2d_3">
      <g>
       <use xlink:href="#mdde9edc3cd" x="182.050909" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_3">
      <!-- 1.0 -->
      <g transform="translate(174.099347 322.182437) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-31" d="M 794 531 
L 1825 531 
L 1825 4091 
L 703 3866 
L 703 4441 
L 1819 4666 
L 2450 4666 
L 2450 531 
L 3481 531 
L 3481 0 
L 794 0 
L 794 531 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-31"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-30" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_4">
     <g id="line2d_4">
      <g>
       <use xlink:href="#mdde9edc3cd" x="236.16" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_4">
      <!-- 1.5 -->
      <g transform="translate(228.208438 322.182437) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-31"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-35" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_5">
     <g id="line2d_5">
      <g>
       <use xlink:href="#mdde9edc3cd" x="290.269091" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_5">
      <!-- 2.0 -->
      <g transform="translate(282.317528 322.182437) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-32" d="M 1228 531 
L 3431 531 
L 3431 0 
L 469 0 
L 469 531 
Q 828 903 1448 1529 
Q 2069 2156 2228 2338 
Q 2531 2678 2651 2914 
Q 2772 3150 2772 3378 
Q 2772 3750 2511 3984 
Q 2250 4219 1831 4219 
Q 1534 4219 1204 4116 
Q 875 4013 500 3803 
L 500 4441 
Q 881 4594 1212 4672 
Q 1544 4750 1819 4750 
Q 2544 4750 2975 4387 
Q 3406 4025 3406 3419 
Q 3406 3131 3298 2873 
Q 3191 2616 2906 2266 
Q 2828 2175 2409 1742 
Q 1991 1309 1228 531 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-32"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-30" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_6">
     <g id="line2d_6">
      <g>
       <use xlink:href="#mdde9edc3cd" x="344.378182" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_6">
      <!-- 2.5 -->
      <g transform="translate(336.426619 322.182437) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-32"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-35" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_7">
     <g id="line2d_7">
      <g>
       <use xlink:href="#mdde9edc3cd" x="398.487273" y="307.584" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_7">
      <!-- 3.0 -->
      <g transform="translate(390.53571 322.182437) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-33" d="M 2597 2516 
Q 3050 2419 3304 2112 
Q 3559 1806 3559 1356 
Q 3559 666 3084 287 
Q 2609 -91 1734 -91 
Q 1441 -91 1130 -33 
Q 819 25 488 141 
L 488 750 
Q 750 597 1062 519 
Q 1375 441 1716 441 
Q 2309 441 2620 675 
Q 2931 909 2931 1356 
Q 2931 1769 2642 2001 
Q 2353 2234 1838 2234 
L 1294 2234 
L 1294 2753 
L 1863 2753 
Q 2328 2753 2575 2939 
Q 2822 3125 2822 3475 
Q 2822 3834 2567 4026 
Q 2313 4219 1838 4219 
Q 1578 4219 1281 4162 
Q 984 4106 628 3988 
L 628 4550 
Q 988 4650 1302 4700 
Q 1616 4750 1894 4750 
Q 2613 4750 3031 4423 
Q 3450 4097 3450 3541 
Q 3450 3153 3228 2886 
Q 3006 2619 2597 2516 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-33"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-30" x="95.410156"/>
      </g>
     </g>
    </g>
   </g>
   <g id="matplotlib.axis_2">
    <g id="ytick_1">
     <g id="line2d_8">
      <defs>
       <path id="m98933f943c" d="M 0 0 
L -3.5 0 
" style="stroke: #000000; stroke-width: 0.8"/>
      </defs>
      <g>
       <use xlink:href="#m98933f943c" x="57.6" y="295.488" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_8">
      <!-- 0 -->
      <g transform="translate(44.2375 299.287219) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-30"/>
      </g>
     </g>
    </g>
    <g id="ytick_2">
     <g id="line2d_9">
      <g>
       <use xlink:href="#m98933f943c" x="57.6" y="241.728" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_9">
      <!-- 2 -->
      <g transform="translate(44.2375 245.527219) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-32"/>
      </g>
     </g>
    </g>
    <g id="ytick_3">
     <g id="line2d_10">
      <g>
       <use xlink:href="#m98933f943c" x="57.6" y="187.968" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_10">
      <!-- 4 -->
      <g transform="translate(44.2375 191.767219) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-34" d="M 2419 4116 
L 825 1625 
L 2419 1625 
L 2419 4116 
z
M 2253 4666 
L 3047 4666 
L 3047 1625 
L 3713 1625 
L 3713 1100 
L 3047 1100 
L 3047 0 
L 2419 0 
L 2419 1100 
L 313 1100 
L 313 1709 
L 2253 4666 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-34"/>
      </g>
     </g>
    </g>
    <g id="ytick_4">
     <g id="line2d_11">
      <g>
       <use xlink:href="#m98933f943c" x="57.6" y="134.208" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_11">
      <!-- 6 -->
      <g transform="translate(44.2375 138.007219) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-36" d="M 2113 2584 
Q 1688 2584 1439 2293 
Q 1191 2003 1191 1497 
Q 1191 994 1439 701 
Q 1688 409 2113 409 
Q 2538 409 2786 701 
Q 3034 994 3034 1497 
Q 3034 2003 2786 2293 
Q 2538 2584 2113 2584 
z
M 3366 4563 
L 3366 3988 
Q 3128 4100 2886 4159 
Q 2644 4219 2406 4219 
Q 1781 4219 1451 3797 
Q 1122 3375 1075 2522 
Q 1259 2794 1537 2939 
Q 1816 3084 2150 3084 
Q 2853 3084 3261 2657 
Q 3669 2231 3669 1497 
Q 3669 778 3244 343 
Q 2819 -91 2113 -91 
Q 1303 -91 875 529 
Q 447 1150 447 2328 
Q 447 3434 972 4092 
Q 1497 4750 2381 4750 
Q 2619 4750 2861 4703 
Q 3103 4656 3366 4563 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-36"/>
      </g>
     </g>
    </g>
    <g id="ytick_5">
     <g id="line2d_12">
      <g>
       <use xlink:href="#m98933f943c" x="57.6" y="80.448" style="stroke: #000000; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_12">
      <!-- 8 -->
      <g transform="translate(44.2375 84.247219) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-38" d="M 2034 2216 
Q 1584 2216 1326 1975 
Q 1069 1734 1069 1313 
Q 1069 891 1326 650 
Q 1584 409 2034 409 
Q 2484 409 2743 651 
Q 3003 894 3003 1313 
Q 3003 1734 2745 1975 
Q 2488 2216 2034 2216 
z
M 1403 2484 
Q 997 2584 770 2862 
Q 544 3141 544 3541 
Q 544 4100 942 4425 
Q 1341 4750 2034 4750 
Q 2731 4750 3128 4425 
Q 3525 4100 3525 3541 
Q 3525 3141 3298 2862 
Q 3072 2584 2669 2484 
Q 3125 2378 3379 2068 
Q 3634 1759 3634 1313 
Q 3634 634 3220 271 
Q 2806 -91 2034 -91 
Q 1263 -91 848 271 
Q 434 634 434 1313 
Q 434 1759 690 2068 
Q 947 2378 1403 2484 
z
M 1172 3481 
Q 1172 3119 1398 2916 
Q 1625 2713 2034 2713 
Q 2441 2713 2670 2916 
Q 2900 3119 2900 3481 
Q 2900 3844 2670 4047 
Q 2441 4250 2034 4250 
Q 1625 4250 1398 4047 
Q 1172 3844 1172 3481 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-38"/>
      </g>
     </g>
    </g>
   </g>
   <g id="line2d_13">
    <path d="M 73.832727 295.488 
L 77.112066 295.463317 
L 80.391405 295.389267 
L 83.670744 295.265851 
L 86.950083 295.093069 
L 90.229421 294.87092 
L 93.50876 294.599405 
L 96.788099 294.278523 
L 100.067438 293.908275 
L 103.346777 293.488661 
L 106.626116 293.01968 
L 109.905455 292.501333 
L 113.184793 291.93362 
L 116.464132 291.31654 
L 119.743471 290.650094 
L 123.02281 289.934281 
L 126.302149 289.169102 
L 129.581488 288.354556 
L 132.860826 287.490645 
L 136.140165 286.577366 
L 139.419504 285.614722 
L 142.698843 284.602711 
L 145.978182 283.541333 
L 149.257521 282.43059 
L 152.53686 281.270479 
L 155.816198 280.061003 
L 159.095537 278.80216 
L 162.374876 277.49395 
L 165.654215 276.136375 
L 168.933554 274.729433 
L 172.212893 273.273124 
L 175.492231 271.767449 
L 178.77157 270.212408 
L 182.050909 268.608 
L 185.330248 266.954226 
L 188.609587 265.251085 
L 191.888926 263.498579 
L 195.168264 261.696705 
L 198.447603 259.845466 
L 201.726942 257.94486 
L 205.006281 255.994887 
L 208.28562 253.995548 
L 211.564959 251.946843 
L 214.844298 249.848771 
L 218.123636 247.701333 
L 221.402975 245.504529 
L 224.682314 243.258358 
L 227.961653 240.962821 
L 231.240992 238.617917 
L 234.520331 236.223647 
L 237.799669 233.780011 
L 241.079008 231.287008 
L 244.358347 228.744639 
L 247.637686 226.152904 
L 250.917025 223.511802 
L 254.196364 220.821333 
L 257.475702 218.081499 
L 260.755041 215.292298 
L 264.03438 212.45373 
L 267.313719 209.565796 
L 270.593058 206.628496 
L 273.872397 203.641829 
L 277.151736 200.605796 
L 280.431074 197.520397 
L 283.710413 194.385631 
L 286.989752 191.201499 
L 290.269091 187.968 
L 293.54843 184.685135 
L 296.827769 181.352904 
L 300.107107 177.971306 
L 303.386446 174.540342 
L 306.665785 171.060011 
L 309.945124 167.530314 
L 313.224463 163.951251 
L 316.503802 160.322821 
L 319.78314 156.645025 
L 323.062479 152.917862 
L 326.341818 149.141333 
L 329.621157 145.315438 
L 332.900496 141.440176 
L 336.179835 137.515548 
L 339.459174 133.541554 
L 342.738512 129.518193 
L 346.017851 125.445466 
L 349.29719 121.323372 
L 352.576529 117.151912 
L 355.855868 112.931085 
L 359.135207 108.660893 
L 362.414545 104.341333 
L 365.693884 99.972408 
L 368.973223 95.554116 
L 372.252562 91.086457 
L 375.531901 86.569433 
L 378.81124 82.003041 
L 382.090579 77.387284 
L 385.369917 72.72216 
L 388.649256 68.007669 
L 391.928595 63.243813 
L 395.207934 58.43059 
L 398.487273 53.568 
" clip-path="url(#pc6e8befb7d)" style="fill: none; stroke: #0000ff; stroke-width: 1.5; stroke-linecap: square"/>
   </g>
   <g id="line2d_14">
    <path d="M 73.832727 295.488 
L 77.112066 293.858909 
L 80.391405 292.229818 
L 83.670744 290.600727 
L 86.950083 288.971636 
L 90.229421 287.342545 
L 93.50876 285.713455 
L 96.788099 284.084364 
L 100.067438 282.455273 
L 103.346777 280.826182 
L 106.626116 279.197091 
L 109.905455 277.568 
L 113.184793 275.938909 
L 116.464132 274.309818 
L 119.743471 272.680727 
L 123.02281 271.051636 
L 126.302149 269.422545 
L 129.581488 267.793455 
L 132.860826 266.164364 
L 136.140165 264.535273 
L 139.419504 262.906182 
L 142.698843 261.277091 
L 145.978182 259.648 
L 149.257521 258.018909 
L 152.53686 256.389818 
L 155.816198 254.760727 
L 159.095537 253.131636 
L 162.374876 251.502545 
L 165.654215 249.873455 
L 168.933554 248.244364 
L 172.212893 246.615273 
L 175.492231 244.986182 
L 178.77157 243.357091 
L 182.050909 241.728 
L 185.330248 240.098909 
L 188.609587 238.469818 
L 191.888926 236.840727 
L 195.168264 235.211636 
L 198.447603 233.582545 
L 201.726942 231.953455 
L 205.006281 230.324364 
L 208.28562 228.695273 
L 211.564959 227.066182 
L 214.844298 225.437091 
L 218.123636 223.808 
L 221.402975 222.178909 
L 224.682314 220.549818 
L 227.961653 218.920727 
L 231.240992 217.291636 
L 234.520331 215.662545 
L 237.799669 214.033455 
L 241.079008 212.404364 
L 244.358347 210.775273 
L 247.637686 209.146182 
L 250.917025 207.517091 
L 254.196364 205.888 
L 257.475702 204.258909 
L 260.755041 202.629818 
L 264.03438 201.000727 
L 267.313719 199.371636 
L 270.593058 197.742545 
L 273.872397 196.113455 
L 277.151736 194.484364 
L 280.431074 192.855273 
L 283.710413 191.226182 
L 286.989752 189.597091 
L 290.269091 187.968 
L 293.54843 186.338909 
L 296.827769 184.709818 
L 300.107107 183.080727 
L 303.386446 181.451636 
L 306.665785 179.822545 
L 309.945124 178.193455 
L 313.224463 176.564364 
L 316.503802 174.935273 
L 319.78314 173.306182 
L 323.062479 171.677091 
L 326.341818 170.048 
L 329.621157 168.418909 
L 332.900496 166.789818 
L 336.179835 165.160727 
L 339.459174 163.531636 
L 342.738512 161.902545 
L 346.017851 160.273455 
L 349.29719 158.644364 
L 352.576529 157.015273 
L 355.855868 155.386182 
L 359.135207 153.757091 
L 362.414545 152.128 
L 365.693884 150.498909 
L 368.973223 148.869818 
L 372.252562 147.240727 
L 375.531901 145.611636 
L 378.81124 143.982545 
L 382.090579 142.353455 
L 385.369917 140.724364 
L 388.649256 139.095273 
L 391.928595 137.466182 
L 395.207934 135.837091 
L 398.487273 134.208 
" clip-path="url(#pc6e8befb7d)" style="fill: none; stroke-dasharray: 5.55,2.4; stroke-dashoffset: 0; stroke: #ff0000; stroke-width: 1.5"/>
   </g>
   <g id="patch_3">
    <path d="M 57.6 307.584 
L 57.6 41.472 
" style="fill: none; stroke: #000000; stroke-width: 0.8; stroke-linejoin: miter; stroke-linecap: square"/>
   </g>
   <g id="patch_4">
    <path d="M 414.72 307.584 
L 414.72 41.472 
" style="fill: none; stroke: #000000; stroke-width: 0.8; stroke-linejoin: miter; stroke-linecap: square"/>
   </g>
   <g id="patch_5">
    <path d="M 57.6 307.584 
L 414.72 307.584 
" style="fill: none; stroke: #000000; stroke-width: 0.8; stroke-linejoin: miter; stroke-linecap: square"/>
   </g>
   <g id="patch_6">
    <path d="M 57.6 41.472 
L 414.72 41.472 
" style="fill: none; stroke: #000000; stroke-width: 0.8; stroke-linejoin: miter; stroke-linecap: square"/>
   </g>
   <g id="text_13">
    <!-- $x^2$ og $2x$ -->
    <g transform="translate(210.84 35.472) scale(0.12 -0.12)">
     <defs>
      <path id="DejaVuSans-Oblique-78" d="M 3841 3500 
L 2234 1784 
L 3219 0 
L 2559 0 
L 1819 1388 
L 531 0 
L -166 0 
L 1556 1844 
L 641 3500 
L 1300 3500 
L 1972 2234 
L 3144 3500 
L 3841 3500 
z
" transform="scale(0.015625)"/>
      <path id="DejaVuSans-20" transform="scale(0.015625)"/>
      <path id="DejaVuSans-6f" d="M 1959 3097 
Q 1497 3097 1228 2736 
Q 959 2375 959 1747 
Q 959 1119 1226 758 
Q 1494 397 1959 397 
Q 2419 397 2687 759 
Q 2956 1122 2956 1747 
Q 2956 2369 2687 2733 
Q 2419 3097 1959 3097 
z
M 1959 3584 
Q 2709 3584 3137 3096 
Q 3566 2609 3566 1747 
Q 3566 888 3137 398 
Q 2709 -91 1959 -91 
Q 1206 -91 779 398 
Q 353 888 353 1747 
Q 353 2609 779 3096 
Q 1206 3584 1959 3584 
z
" transform="scale(0.015625)"/>
      <path id="DejaVuSans-67" d="M 2906 1791 
Q 2906 2416 2648 2759 
Q 2391 3103 1925 3103 
Q 1463 3103 1205 2759 
Q 947 2416 947 1791 
Q 947 1169 1205 825 
Q 1463 481 1925 481 
Q 2391 481 2648 825 
Q 2906 1169 2906 1791 
z
M 3481 434 
Q 3481 -459 3084 -895 
Q 2688 -1331 1869 -1331 
Q 1566 -1331 1297 -1286 
Q 1028 -1241 775 -1147 
L 775 -588 
Q 1028 -725 1275 -790 
Q 1522 -856 1778 -856 
Q 2344 -856 2625 -561 
Q 2906 -266 2906 331 
L 2906 616 
Q 2728 306 2450 153 
Q 2172 0 1784 0 
Q 1141 0 747 490 
Q 353 981 353 1791 
Q 353 2603 747 3093 
Q 1141 3584 1784 3584 
Q 2172 3584 2450 3431 
Q 2728 3278 2906 2969 
L 2906 3500 
L 3481 3500 
L 3481 434 
z
" transform="scale(0.015625)"/>
     </defs>
     <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(0 0.765625)"/>
     <use xlink:href="#DejaVuSans-32" transform="translate(63.645833 39.046875) scale(0.7)"/>
     <use xlink:href="#DejaVuSans-20" transform="translate(110.916341 0.765625)"/>
     <use xlink:href="#DejaVuSans-6f" transform="translate(142.703451 0.765625)"/>
     <use xlink:href="#DejaVuSans-67" transform="translate(203.885091 0.765625)"/>
     <use xlink:href="#DejaVuSans-20" transform="translate(267.361654 0.765625)"/>
     <use xlink:href="#DejaVuSans-32" transform="translate(299.148763 0.765625)"/>
     <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(362.77181 0.765625)"/>
    </g>
   </g>
   <g id="legend_1">
    <g id="patch_7">
     <path d="M 64.6 78.82825 
L 108.9 78.82825 
Q 110.9 78.82825 110.9 76.82825 
L 110.9 48.472 
Q 110.9 46.472 108.9 46.472 
L 64.6 46.472 
Q 62.6 46.472 62.6 48.472 
L 62.6 76.82825 
Q 62.6 78.82825 64.6 78.82825 
z
" style="fill: #ffffff; opacity: 0.8; stroke: #cccccc; stroke-linejoin: miter"/>
    </g>
    <g id="line2d_15">
     <path d="M 66.6 54.570437 
L 76.6 54.570437 
L 86.6 54.570437 
" style="fill: none; stroke: #0000ff; stroke-width: 1.5; stroke-linecap: square"/>
    </g>
    <g id="text_14">
     <!-- $x^2$ -->
     <g transform="translate(94.6 58.070437) scale(0.1 -0.1)">
      <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(0 0.765625)"/>
      <use xlink:href="#DejaVuSans-32" transform="translate(63.645833 39.046875) scale(0.7)"/>
     </g>
    </g>
    <g id="line2d_16">
     <path d="M 66.6 69.248562 
L 76.6 69.248562 
L 86.6 69.248562 
" style="fill: none; stroke-dasharray: 5.55,2.4; stroke-dashoffset: 0; stroke: #ff0000; stroke-width: 1.5"/>
    </g>
    <g id="text_15">
     <!-- $2x$ -->
     <g transform="translate(94.6 72.748562) scale(0.1 -0.1)">
      <use xlink:href="#DejaVuSans-32" transform="translate(0 0.78125)"/>
      <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(63.623047 0.78125)"/>
     </g>
    </g>
   </g>
  </g>
 </g>
 <defs>
  <clipPath id="pc6e8befb7d">
   <rect x="57.6" y="41.472" width="357.12" height="266.112"/>
  </clipPath>
 </defs>
</svg>


Eksempelet ovenfor lager en [[Numpy\|Numpy]] array med 100 `x`-verdier mellom 0 og 3. Deretter lager den to nye arrays `y1` og `y2` som vil inneholde funksjonsverdiene til $x^{2}$ og $2x$ for $x \in [0,3]$. 

`ax.plot()` kan ta inn mange flere argumenter enn hva jeg brukte ovenfor. Du finner en full oversikt i [dokumentasjonen](https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.plot.html). I eksempelet mitt brukte jeg 
- `c` som definerer fargen på grafen.
- `linestyle` som definerer hvordan linja mellom punktene skal tegnes.
- `label` som definerer hvilket navn som skal stå i forklaringsboksen.

I dette plottet har jeg også lagt inn en forklaringsboks med `ax.legend()` og en tittel på diagrammet med `ax.set_title()`.[^1] Til slutt er det viktig å gi beskjed om at plottet skal vises på skjermen med `fig.show()`. Du kan eventuelt lagre figuren med `fig.savefig("")`.

### Sett egenskaper ved subplottet
Vi har allerede endret tittelen til subplottet med `ax.set_title()`. Vi kan også endre mange andre egenskaper ved subplottet. De viktigste egenskapene er:
- `ax.set_xlim(0, 3)` sier at `x`-verdiene som skal vises er mellom 0 og 3
- `ax.set_ylim(-2, 3)` sier at `y`-verdiene som skal vises er mellom -2 og 3
- `ax.set_xlabel("Navn på x-akse")` setter navnet som skal vises langs $x$-aksen. 
- `ax.set_ylabel("Navn på y-akse")` setter navnet som skal vises langs $y$-aksen. 
- `ax.grid()` gir et rutenett i bakgrunnen

## Tips

### Lag flere subplots i samme figur
Hvis du vil ha flere plott på den samme figuren så gir du argumenter til `subplots`. Hvis du ønsker å ha 2 rader med 3 plott i hver rad kan du skrive:

```python
fig, ax = plt.subplots(2,3)
```

`ax` er nå en liste med 6 koordinatsystemobjekter. For å plotte noe i øverste venstre koordinatsystem så bruker du `ax[0].plot(x_verdier, y_verdier)` og for å plotte til det nedre, midterste koordinatsystemet så skriver du `ax[4].plot(x_verdier, y_verdier)`.

### Lag fine plott med koordinatakser med piler
I lærebøker så er det vanlig at koordinataksene skjærer i origo og er merket med piler i positiv retning. Du kan få denne stilen ved å følge [dette eksempelet](https://matplotlib.org/3.3.4/gallery/recipes/centered_spines_with_arrows.html).

![Plott av sinusfunksjon hvor koordinataksene skjærer origo og har piler som markerer positiv retning](https://matplotlib.org/3.3.4/_images/sphx_glr_centered_spines_with_arrows_001.png)

## Velg stilark
Matplotlib kommer med mange ferdige stilark, se [hjemmesiden](https://matplotlib.org/stable/gallery/style_sheets/style_sheets_reference.html) for et galleri med eksempler. Du velger stilark med

```python
plt.style.use('default')
```

Jeg liker `ggplot`. For bruk på sider med mørk bakgrunn bruker jeg gjerne `dark_background` og lagrer figurene mine med `fig.savefig("filnavn.svg", transparent=True)`. Da vil bakgrunnen være gjennomsiktig, men grafene får farger som fungerer fint på mørke bakgrunner.

[^1]: Jeg har valgt å bruke `$$` rundt matematikk i forklaringstekster og titler. All tekst som står mellom dollartegnene blir tolket som [LaTeX](https://www.mn.uio.no/ifi/tjenester/it/hjelp/latex/latex-for-nybegynnere.pdf). Det gir et profesjonelt og flott utseende.