---
{"dg-publish":true,"permalink":"/Kunnskap/Den naturlige logaritmen/","title":"Den naturlige logaritmen","tags":["matematikk","s2"]}
---


# Den naturlige logaritmen
Den naturlige logaritmen $\ln x$ kan defineres på følgende måte:

>[!important] Definisjon av $\ln x$
Den naturlige logaritmen $\ln x$ er den [[Inverse funksjoner\|inverse funksjonen]] til $e^{x}$ slik at 
> $$ e^{\ln x}=x $$
> 
> Siden $e^{x}>0$ vil også $e^{\ln x}>0$. Ut fra likheten over så ser vi at $x>0$.
> 
> Definisjonsmengden er dermed alle positive tall: $D_{f} = \langle 0, \infty \rangle = \{x \mid x > 0\}$.
> Verdimengden er alle reelle tall: $V_{f}= \langle -\infty, \infty\rangle =\{x \mid x\in\mathbb{R}\}$.


<svg xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 360 216" xmlns="http://www.w3.org/2000/svg" version="1.1">
 <metadata>
  <rdf:RDF xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:cc="http://creativecommons.org/ns#" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
   <cc:Work>
    <dc:type rdf:resource="http://purl.org/dc/dcmitype/StillImage"/>
    <dc:date>2023-10-12T22:50:09.772077</dc:date>
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
   <path d="M 0 216 
L 360 216 
L 360 0 
L 0 0 
L 0 216 
z
" style="fill: none"/>
  </g>
  <g id="axes_1">
   <g id="patch_2">
    <path d="M 45 192.24 
L 324 192.24 
L 324 25.92 
L 45 25.92 
L 45 192.24 
z
" style="fill: none"/>
   </g>
   <g id="matplotlib.axis_1">
    <g id="xtick_1">
     <g id="line2d_1">
      <defs>
       <path id="mdb296a22df" d="M 0 0 
L 0 3.5 
" style="stroke: #ffffff; stroke-width: 0.8"/>
      </defs>
      <g>
       <use xlink:href="#mdb296a22df" x="57.681818" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_1">
      <!-- 0.0 -->
      <g style="fill: #ffffff" transform="translate(49.730256 110.884591) scale(0.1 -0.1)">
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
       <use xlink:href="#mdb296a22df" x="89.386364" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_2">
      <!-- 0.5 -->
      <g style="fill: #ffffff" transform="translate(81.434801 110.884591) scale(0.1 -0.1)">
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
       <use xlink:href="#mdb296a22df" x="121.090909" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_3">
      <!-- 1.0 -->
      <g style="fill: #ffffff" transform="translate(113.139347 110.884591) scale(0.1 -0.1)">
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
       <use xlink:href="#mdb296a22df" x="152.795455" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_4">
      <!-- 1.5 -->
      <g style="fill: #ffffff" transform="translate(144.843892 110.884591) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-31"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-35" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_5">
     <g id="line2d_5">
      <g>
       <use xlink:href="#mdb296a22df" x="184.5" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_5">
      <!-- 2.0 -->
      <g style="fill: #ffffff" transform="translate(176.548438 110.884591) scale(0.1 -0.1)">
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
       <use xlink:href="#mdb296a22df" x="216.204545" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_6">
      <!-- 2.5 -->
      <g style="fill: #ffffff" transform="translate(208.252983 110.884591) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-32"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-35" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_7">
     <g id="line2d_7">
      <g>
       <use xlink:href="#mdb296a22df" x="247.909091" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_7">
      <!-- 3.0 -->
      <g style="fill: #ffffff" transform="translate(239.957528 110.884591) scale(0.1 -0.1)">
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
    <g id="xtick_8">
     <g id="line2d_8">
      <g>
       <use xlink:href="#mdb296a22df" x="279.613636" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_8">
      <!-- 3.5 -->
      <g style="fill: #ffffff" transform="translate(271.662074 110.884591) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-33"/>
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-35" x="95.410156"/>
      </g>
     </g>
    </g>
    <g id="xtick_9">
     <g id="line2d_9">
      <g>
       <use xlink:href="#mdb296a22df" x="311.318182" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_9">
      <!-- 4.0 -->
      <g style="fill: #ffffff" transform="translate(303.366619 110.884591) scale(0.1 -0.1)">
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
       <use xlink:href="#DejaVuSans-2e" x="63.623047"/>
       <use xlink:href="#DejaVuSans-30" x="95.410156"/>
      </g>
     </g>
    </g>
   </g>
   <g id="matplotlib.axis_2">
    <g id="ytick_1">
     <g id="line2d_10">
      <defs>
       <path id="m73d546e815" d="M 0 0 
L -3.5 0 
" style="stroke: #ffffff; stroke-width: 0.8"/>
      </defs>
      <g>
       <use xlink:href="#m73d546e815" x="57.681818" y="192.24" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_10">
      <!-- −3 -->
      <g style="fill: #ffffff" transform="translate(35.939631 196.039219) scale(0.1 -0.1)">
       <defs>
        <path id="DejaVuSans-2212" d="M 678 2272 
L 4684 2272 
L 4684 1741 
L 678 1741 
L 678 2272 
z
" transform="scale(0.015625)"/>
       </defs>
       <use xlink:href="#DejaVuSans-2212"/>
       <use xlink:href="#DejaVuSans-33" x="83.789062"/>
      </g>
     </g>
    </g>
    <g id="ytick_2">
     <g id="line2d_11">
      <g>
       <use xlink:href="#m73d546e815" x="57.681818" y="160.255385" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_11">
      <!-- −2 -->
      <g style="fill: #ffffff" transform="translate(35.939631 164.054603) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-2212"/>
       <use xlink:href="#DejaVuSans-32" x="83.789062"/>
      </g>
     </g>
    </g>
    <g id="ytick_3">
     <g id="line2d_12">
      <g>
       <use xlink:href="#m73d546e815" x="57.681818" y="128.270769" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_12">
      <!-- −1 -->
      <g style="fill: #ffffff" transform="translate(35.939631 132.069988) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-2212"/>
       <use xlink:href="#DejaVuSans-31" x="83.789062"/>
      </g>
     </g>
    </g>
    <g id="ytick_4">
     <g id="line2d_13">
      <g>
       <use xlink:href="#m73d546e815" x="57.681818" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_13">
      <!-- 0 -->
      <g style="fill: #ffffff" transform="translate(44.319318 100.085373) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-30"/>
      </g>
     </g>
    </g>
    <g id="ytick_5">
     <g id="line2d_14">
      <g>
       <use xlink:href="#m73d546e815" x="57.681818" y="64.301538" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_14">
      <!-- 1 -->
      <g style="fill: #ffffff" transform="translate(44.319318 68.100757) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-31"/>
      </g>
     </g>
    </g>
    <g id="ytick_6">
     <g id="line2d_15">
      <g>
       <use xlink:href="#m73d546e815" x="57.681818" y="32.316923" style="fill: #ffffff; stroke: #ffffff; stroke-width: 0.8"/>
      </g>
     </g>
     <g id="text_15">
      <!-- 2 -->
      <g style="fill: #ffffff" transform="translate(44.319318 36.116142) scale(0.1 -0.1)">
       <use xlink:href="#DejaVuSans-32"/>
      </g>
     </g>
    </g>
   </g>
   <g id="line2d_16">
    <path d="M 59.143045 217 
L 59.775842 205.370324 
L 60.537322 195.449944 
L 61.552629 185.71972 
L 62.567936 178.269412 
L 63.83707 170.883922 
L 65.106204 164.88795 
L 66.629165 158.920035 
L 68.152125 153.892489 
L 69.928913 148.879049 
L 71.7057 144.545997 
L 73.736314 140.220806 
L 75.766929 136.411438 
L 78.05137 132.606796 
L 80.589638 128.850616 
L 83.127905 125.489555 
L 85.92 122.15954 
L 88.965921 118.883194 
L 92.26567 115.67588 
L 95.819244 112.547488 
L 99.626646 109.503863 
L 103.687875 106.547912 
L 108.00293 103.680438 
L 112.825639 100.753207 
L 117.902174 97.936458 
L 123.486364 95.100111 
L 129.578206 92.268285 
L 135.923876 89.562985 
L 143.031026 86.78212 
L 150.645829 84.048674 
L 158.768286 81.36952 
L 167.652224 78.675295 
L 177.297641 75.986226 
L 187.704539 73.317938 
L 199.126744 70.624795 
L 211.31043 67.981981 
L 224.509423 65.345717 
L 238.977549 62.685601 
L 254.71481 60.02315 
L 271.721204 57.37518 
L 290.250559 54.719632 
L 310.302875 52.074353 
L 311.318182 51.946062 
L 311.318182 51.946062 
" clip-path="url(#p2f17477ee4)" style="fill: none; stroke: #0000ff; stroke-width: 1.5; stroke-linecap: square"/>
   </g>
   <g id="line2d_17">
    <path d="M 78.52905 -1 
L 79.828157 4.708247 
L 81.604945 11.509802 
L 83.381732 17.370894 
L 85.15852 22.473968 
L 86.935307 26.957145 
L 88.965921 31.45721 
L 90.996536 35.408694 
L 93.02715 38.906147 
L 95.311591 42.389592 
L 97.596032 45.474295 
L 100.1343 48.512377 
L 102.672568 51.207656 
L 105.464662 53.841728 
L 108.510584 56.385216 
L 111.556505 58.641102 
L 114.856253 60.813737 
L 118.409828 62.88945 
L 122.21723 64.859758 
L 126.532285 66.82934 
L 131.101167 68.662436 
L 136.177703 70.448935 
L 141.761892 72.164917 
L 147.853735 73.794502 
L 154.453231 75.328359 
L 161.814208 76.809837 
L 170.190491 78.259851 
L 179.328256 79.61394 
L 189.735154 80.927849 
L 201.411186 82.1755 
L 214.864005 83.383194 
L 230.093612 84.522948 
L 247.60766 85.607694 
L 267.913802 86.639118 
L 291.77352 87.622389 
L 311.318182 88.29 
L 311.318182 88.29 
" clip-path="url(#p2f17477ee4)" style="fill: none; stroke: #ff0000; stroke-width: 1.5; stroke-linecap: square"/>
   </g>
   <g id="line2d_18">
    <defs>
     <path id="mf57ab0e9a9" d="M 3 0 
L -3 -3 
L -3 3 
z
" style="stroke: #ffffff; stroke-linejoin: miter"/>
    </defs>
    <g>
     <use xlink:href="#mf57ab0e9a9" x="324" y="96.286154" style="fill: #ffffff; stroke: #ffffff; stroke-linejoin: miter"/>
    </g>
   </g>
   <g id="line2d_19">
    <defs>
     <path id="mbafd00b46c" d="M 0 -3 
L -3 3 
L 3 3 
z
" style="stroke: #ffffff; stroke-linejoin: miter"/>
    </defs>
    <g>
     <use xlink:href="#mbafd00b46c" x="57.681818" y="25.92" style="fill: #ffffff; stroke: #ffffff; stroke-linejoin: miter"/>
    </g>
   </g>
   <g id="patch_3">
    <path d="M 57.681818 192.24 
L 57.681818 25.92 
" style="fill: none; stroke: #ffffff; stroke-width: 0.8; stroke-linejoin: miter; stroke-linecap: square"/>
   </g>
   <g id="patch_4">
    <path d="M 324 192.24 
L 324 25.92 
" style="fill: none"/>
   </g>
   <g id="patch_5">
    <path d="M 45 96.286154 
L 324 96.286154 
" style="fill: none; stroke: #ffffff; stroke-width: 0.8; stroke-linejoin: miter; stroke-linecap: square"/>
   </g>
   <g id="patch_6">
    <path d="M 45 25.92 
L 324 25.92 
" style="fill: none"/>
   </g>
   <g id="text_16">
    <!-- $\ln x$ og $(\ln x)'$ -->
    <g style="fill: #ffffff" transform="translate(147.12 19.92) scale(0.12 -0.12)">
     <defs>
      <path id="DejaVuSans-6c" d="M 603 4863 
L 1178 4863 
L 1178 0 
L 603 0 
L 603 4863 
z
" transform="scale(0.015625)"/>
      <path id="DejaVuSans-6e" d="M 3513 2113 
L 3513 0 
L 2938 0 
L 2938 2094 
Q 2938 2591 2744 2837 
Q 2550 3084 2163 3084 
Q 1697 3084 1428 2787 
Q 1159 2491 1159 1978 
L 1159 0 
L 581 0 
L 581 3500 
L 1159 3500 
L 1159 2956 
Q 1366 3272 1645 3428 
Q 1925 3584 2291 3584 
Q 2894 3584 3203 3211 
Q 3513 2838 3513 2113 
z
" transform="scale(0.015625)"/>
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
      <path id="DejaVuSans-28" d="M 1984 4856 
Q 1566 4138 1362 3434 
Q 1159 2731 1159 2009 
Q 1159 1288 1364 580 
Q 1569 -128 1984 -844 
L 1484 -844 
Q 1016 -109 783 600 
Q 550 1309 550 2009 
Q 550 2706 781 3412 
Q 1013 4119 1484 4856 
L 1984 4856 
z
" transform="scale(0.015625)"/>
      <path id="DejaVuSans-29" d="M 513 4856 
L 1013 4856 
Q 1481 4119 1714 3412 
Q 1947 2706 1947 2009 
Q 1947 1309 1714 600 
Q 1481 -109 1013 -844 
L 513 -844 
Q 928 -128 1133 580 
Q 1338 1288 1338 2009 
Q 1338 2731 1133 3434 
Q 928 4138 513 4856 
z
" transform="scale(0.015625)"/>
      <path id="Cmsy10-30" d="M 225 347 
Q 184 359 184 409 
L 966 3316 
Q 1003 3434 1093 3506 
Q 1184 3578 1300 3578 
Q 1450 3578 1564 3479 
Q 1678 3381 1678 3231 
Q 1678 3166 1644 3084 
L 488 319 
Q 466 275 428 275 
Q 394 275 320 306 
Q 247 338 225 347 
z
" transform="scale(0.015625)"/>
     </defs>
     <use xlink:href="#DejaVuSans-6c" transform="translate(0 0.584375)"/>
     <use xlink:href="#DejaVuSans-6e" transform="translate(27.783203 0.584375)"/>
     <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(107.397786 0.584375)"/>
     <use xlink:href="#DejaVuSans-20" transform="translate(166.577473 0.584375)"/>
     <use xlink:href="#DejaVuSans-6f" transform="translate(198.364583 0.584375)"/>
     <use xlink:href="#DejaVuSans-67" transform="translate(259.546223 0.584375)"/>
     <use xlink:href="#DejaVuSans-20" transform="translate(323.022786 0.584375)"/>
     <use xlink:href="#DejaVuSans-28" transform="translate(354.809895 0.584375)"/>
     <use xlink:href="#DejaVuSans-6c" transform="translate(393.823567 0.584375)"/>
     <use xlink:href="#DejaVuSans-6e" transform="translate(421.60677 0.584375)"/>
     <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(501.221353 0.584375)"/>
     <use xlink:href="#DejaVuSans-29" transform="translate(560.40104 0.584375)"/>
     <use xlink:href="#Cmsy10-30" transform="translate(600.371743 38.865625) scale(0.7)"/>
    </g>
   </g>
   <g id="legend_1">
    <g id="patch_7">
     <path d="M 262.1 187.24 
L 317 187.24 
Q 319 187.24 319 185.24 
L 319 154.461875 
Q 319 152.461875 317 152.461875 
L 262.1 152.461875 
Q 260.1 152.461875 260.1 154.461875 
L 260.1 185.24 
Q 260.1 187.24 262.1 187.24 
z
" style="opacity: 0.8; stroke: #cccccc; stroke-linejoin: miter"/>
    </g>
    <g id="line2d_20">
     <path d="M 264.1 160.560313 
L 274.1 160.560313 
L 284.1 160.560313 
" style="fill: none; stroke: #0000ff; stroke-width: 1.5; stroke-linecap: square"/>
    </g>
    <g id="text_17">
     <!-- $\ln(x)$ -->
     <g style="fill: #ffffff" transform="translate(292.1 164.060313) scale(0.1 -0.1)">
      <use xlink:href="#DejaVuSans-6c" transform="translate(0 0.015625)"/>
      <use xlink:href="#DejaVuSans-6e" transform="translate(27.783203 0.015625)"/>
      <use xlink:href="#DejaVuSans-28" transform="translate(91.162109 0.015625)"/>
      <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(130.175781 0.015625)"/>
      <use xlink:href="#DejaVuSans-29" transform="translate(189.355469 0.015625)"/>
     </g>
    </g>
    <g id="line2d_21">
     <path d="M 264.1 177.14 
L 274.1 177.14 
L 284.1 177.14 
" style="fill: none; stroke: #ff0000; stroke-width: 1.5; stroke-linecap: square"/>
    </g>
    <g id="text_18">
     <!-- $\frac{1}{x}$ -->
     <g style="fill: #ffffff" transform="translate(292.1 180.64) scale(0.1 -0.1)">
      <use xlink:href="#DejaVuSans-31" transform="translate(0 43.965625) scale(0.7)"/>
      <use xlink:href="#DejaVuSans-Oblique-78" transform="translate(2 -25.565625) scale(0.7)"/>
      <path d="M 0 18.965625 
L 0 25.215625 
L 44.536133 25.215625 
L 44.536133 18.965625 
L 0 18.965625 
z
"/>
     </g>
    </g>
   </g>
  </g>
 </g>
 <defs>
  <clipPath id="p2f17477ee4">
   <rect x="45" y="25.92" width="279" height="166.32"/>
  </clipPath>
 </defs>
</svg>

```mathpad
plot(log(x),1/x, [-1,4],[-4,2])==?
```

## Den deriverte av ln x
$$
\big( \ln (x) \big) '=\frac{1}{x}
$$

Merk at selv om $g(x)=\frac{1}{x}$ er definert for $x\in \mathbb{R} \setminus 0$ så er den deriverte av logaritmefunksjonen kun definert for $x>0$. 

Funksjonen $f(x)=\ln x$ har definisjonsmengde $\{ x \mid x>0 \}$. Derfor kan ikke den deriverte ha noe *større* definisjonsmengde enn dette. For å derivere en funksjon så den være kontinuerlig i punktet. Det gir ikke mening å snakke om vekstfarten til $f$ i $x=-2$ siden $f(-2)$ ikke eksisterer.

>[!important] Beviset for $(\ln x)'=\frac{1}{x}$
>Vi vet at
>$$
>e^{\ln x}=x
>$$
>
>For å bevise $(\ln x)'=\frac{1}{x}$ så deriverer vi hver side av likningen ovenfor og sammenligner svarene. Hvis vi deriverer den høyre siden av får vi at 
>$$
>(x)' = 1
>$$
>Vi kan også forsøke å derivere den venstre siden av likningen ved hjelp av [[kjerneregelen\|kjerneregelen]]. Vi setter da $u=\ln x$ og får
>$$
>(e^{\ln x})' = (e^{u})'\cdot u'=e^{u}\cdot (\ln x)'=\underbrace{ e^{\ln x} }_{ =x }\cdot (\ln x)'=x\cdot (\ln x)'
>$$
>
>Foreløpig kommer vi ikke lengre, siden vi enda ikke har bevist hva den deriverte av $\ln x$ er. Her kommer derfor den geniale ideen inn – vi sammenligner resultatene av derivasjonene.
>
>Siden vi vet at $e^{\ln x}=x$ så må $(e^{\ln x})'=x'$. Derfor må også:
>$$
\begin{aligned}
(e^{\ln x})'&=x'\\
x\cdot (\ln x)' &= 1 \\
(\ln x)' &= \frac{1}{x} && {\mathbb{Q.E.D.}} \\
\end{aligned}
$$

## Den integrerte av ln x

$$
\int \ln(x) \, \mathrm{d}x = x(\ln(x)-1)+C
$$

> [!tip] Bevis for integralet
> Det er ikke så lett å integrere $\ln (x)$, du er nødt til å bruke et triks og delvis integrasjon.
>
> La $f(x)=\ln (x)$. Ved å sette $\ln (x)=1\cdot \ln (x)$ så kan vi bruke delvis integrasjon
>
> $$ \int \ln (x) \, \mathrm{d}x =\int 1\cdot \ln (x) \, \mathrm{d}x =x\cdot \ln (x)-\int x\cdot \frac{1}{x} \, \mathrm{d}x $$
> Vi trekker sammen og får
> $$ x\cdot\ln (x)-\int 1 \, \mathrm{d}x =x \cdot\ln (x)-x+C=x(\ln(x)-1)+C $$
