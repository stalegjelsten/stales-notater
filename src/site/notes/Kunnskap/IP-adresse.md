---
{"dg-publish":true,"permalink":"/Kunnskap/IP-adresse/","title":"IP-adresse","tags":["ikt100","it","it1","nettverk"]}
---


# IP-adresse

Hver enhet som skal bruke nettverket må ha en unik Internet Protocol-adresse (<abbr>IP</abbr>-adresse).

Det finnes to ulike typer IP-adresser: [[Kunnskap/IP-adresse#IPv4\|IPv4]] og [[Kunnskap/IP-adresse#IPv6\|IPv6]].

## IPv4
Består av 32 bits, altså $2^{32}=4{,}29 \cdot 10^{9}$ adresser. Vanlig notasjon er 4 segmenter med tall fra 0–255, på denne måten: `10.120.42.241`. 

## IPv6
Består av 128 bits, altså $2^{128}=7{,}9 \cdot 10^{28}$ adresser. Det er vanlig å 8 segmenter  (hextet) med 4 heksadesimale tall (`0-f`) på denne måten: `2001:0db8:0000:0000:0000:ff00:0042:8329`

IPv6-adresser kan forkortes på følgende måter
1. Fjerne alle nuller i starten av et segment (hextet):
	1. Full: ``k2001:0db8:0000:0000:0000:ff00:0042:8329`
	2. Forkortet: `2001:db8:0:0:0:ff00:42:8329`
2. Segmenter med 0000 kan byttes ut med `::`. Dette kan kun gjøres en gang per adresse.
	1. Full: `2001:0db8:0000:0000:0000:ff00:0042:8329`
	2. Forkortet: `2001:db8::ff00:42:8329`


<iframe src="https://www.youtube.com/embed/0QI6I6APomE?si=uaEuk8h5hHtEiwcu" class="youtube" title="" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
