---
title: Základy programování v JavaScriptu
---

Otázka 7: Základy programování v JavaScriptu
============================================

> Zadání
> ------
> 
> Proměnné (jednoduché datové typy, pole), operátory, podmíněné příkazy (if, switch, ternární operátor), cykly (for, do while, while).
> 
> *Spotka, kalendář, fotogalerie (náhledy), tabulka dat – výpisy pomocí cyklů, formátování pomocí podmínek.*

No teoreticky asi není třeba moc vysvětlovat, maximálně tak ternární operátor. Ten funguje takhle:

```js
a = Math.random() >= 0.5 ? "Ano" : "Ne";
```

a odpovídá to takovéto podmínce:

```js
if (Math.random() >= 0.5){
    a = "Ano";
}
else{
    a = "Ne";
}
```

Výhoda je asi jasná, je to kratší.

Pojďme tedy na příklady (dají se normálně stáhnout):

* [Stopky](download/otazka07a.html)
* [Kalendář (byl to nějaký test, rychle udělaná varianta, přidám vysvětlivky a nepřehledný části kódu změním)](download/otazka07b.html)
* [Fotogalerie - viz otázka 6](download/otazka06.html)
