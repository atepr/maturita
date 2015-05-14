---
title: HTML - Layout
---

Otázka 2: Layout
================

> Zadání
> ------
> 
> **Layout**  
> Rozvržení stránky - div.
> 
> **Div**  
> Velikost, umístění, obtékání a další vlastnosti bloků.

Stránka je většinou dělena do několika částí, jako je hlavička, menu, obsah, atd.

Dříve se toto dělení (rozvržení) dělalo pomocí bloků div, To bylo před příchodem HTML5. HTML 5 však nyní přišlo s novými značkami právě pro tvorbu layoutu, které vždy dávají určité sekci určitý význam. To pomůže např. vyhledávačům lépe pochopit obsah stránky.

Zde je ukázka HTML rozvržení. V HTML4 by byly pouze pozicované `<div>`.

![layout html5][1]

Dělení layout v HTML5
---------------------

Tag         | Význam
------------|------------------------
`<header>`  | hlavička (záhlaví)
`<nav>`     | navigační menu
`<article>` | článek
`<section>` | oddíl
`<asside>`  | boční panel
`<footer>`  | patička (zápatí)
`<div>`     | obecný blok

------------------------------------------

##`<header>`

`<header>` slouží jako hlavička stránky (neplést s hlavičkou dokumentu). Header zpravidla obsahuje nadpis h1, případně dva nadpisy sloučené pomocí tagu hgroup. Nadpisy se v tomto případě váží k celému webu (jako vše v header), ale header můžeme stejně tak vložit i do dalších sekcí stránky. Header dále zpravidla obsahuje obrázek s logem, vyhledávací pole nebo např. možnost výběru jazyka.

##`<nav>`

`<nav>` obsahuje navigační prvky. Může být součástí header nebo stát samostatně pod ním. Můžeme ho samozřejmě použít kdekoli na stránce, ale zvykem je mít navigaci pod hlavičkou. Obvykle obsahuje nastylovaný seznam ul, jehož položky reprezentují odkazy na jednotlivé podstránky.

##`<article>`

`<article>` tvoří článek, popis určitého druhu (např. výrobku), popis nějaké kulturní akce, apod. Article by měla být kompletní jednotka přenositelná z jednoho webu do jiného.

##`<section>`

`<section>` se používá zejména k označení "těla" dokumentu mezi hlavičkou a patičkou. Právě zde se nalézá samotný článek nebo články.

##`<asside>`

`<asside>` použijeme pro boční panely, obsahující doplňkové informace.

##`<footer>`

`<footer>` použijeme pro zápatí celého webu. Obdobně jako záhlaví může být zápatí součástí článku (article) nebo na konci každého oddílu (section).

##`<div>`

`<div>` Obecný blok div použijeme na seskupení jednotlivých částí stránky. Blok section bychom měli použít k seskupení pouze tématicky příbuzných částí, nikoliv pro seskupení všech bloků webu. K tomuto účelu byl ponechán blok div.

#Vlastnosti prvků

![box model][2]

* Float
    * None- Bez obtékání. Používá se hlavně jako obalový blok.
    * Left- S obtékáním vlevo.
    * Right- S obtékáním vpravo.
* Clear
    * Both- umístěn pod všemi předchozími bloky s libovolným obtékáním.
    * Left- umístěn pod bloky, které mají float:left.
    * Right- umístěn pod bloky, které mají float:right
* overflow
    * Visible- obsah bloku přeteče zadanou výšku bloku.
    * Hidden- obsah bloku bude oříznut podle nastavené výšky bloku.
    * Auto- bude-li obsah delší, vytvoří se u bloku posuvník.
    * Scroll- blok bude mít posuvník i tehdy, bude-li obsah kratší.
* Padding- Vnitřní okraj
* Margin- Vnější okraj
* Border- Ohraničení
* Width- vnitřní šířka bloku
* Height- vnitřní výška bloku

[1]: images/wa02_layout.png
[2]: images/wa02_boxmodel.gif
