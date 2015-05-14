---
title: Tabulky, obrázky, hypertextové odkazy
---

Otázka 3: Tabulky, obrázky, hypertextové odkazy
===============================================

> Zadání
> ------
> 
> **Tabulky**  
> Struktura tabulky, typy buněk, slučování buněk. Příklady formátování pomocí css.
> 
> **Obrázky**  
> URL, velikost, obtékání textem. Příklady formátování pomocí css.
> 
> **Hypertextové odkazy**  
> Absolutní a relativní url, cíl odkazu, titulek. Příklady formátování pomocí css.

#Tabulky

##Struktura tabulky

Tag         | Význam
------------|------------------------------------------------
`<table>`   | Tag který hraničuje tabulku
`<tr>`      | Tag který hraničuje řádek tabulky
`<td>`      | Tag který hraničuje sloupec (buňku tabulky)
`<th>`      | Stejný jako `<td>` pouze tučně, používá se v nadpisech

##Atributy tabulky

Atribut     | Význam
------------|------------------------------------------------
border      | Ohraničení, používá se u tagu `<table>`
cellpadding	| vnitřní okraj buněk (v pixelech), čili vzdálenost textu od rámečku. Taktéž atribut tagu `<table>`
cellspacing	| vnější okraj buněk (vně rámečku). opět u tagu `<table>`
rowspan     | sloučení řádků
colspan     | sloučení buňek

**Poznámka:** border, cellpadding a cellspacing jsou zastaralé a používají se místo nich CSS styly.

![Tabulka][1]

Tabulky potom můžeme take stylovat pomocí CSS stylů můžeme nastavovat napřiklad: width, height, color, background-color, atd .. . Tyto atributy můžeme psát do style="", a nebo je definovat v dokumentu `<style>`, nebo v externím souboru.

#Obrázky

V html se obrázky vkládají nepárovým tagem `<img>`.

##Atributy

Atribut     | Význam
------------|------------------------------------------------
src         | cesta k obrázku
alt         | alternativní text(povinný)
title       | titulek
width       | šířka
height      | výška

![obr][2]

##Obtékání obrázků

Obtékání se dělá CSS vlastností float, zarovnání na řádku CSS vlastností vertical-align.

Normálně prvky obtékané nejsou. Výchozí hodnota je tedy none. Aby mohl být prvek obtékaný, musí mít nastavenou šířku -- width.

Obtékaný prvek je vyjmut z toku dokumentu (stejně jako position: absolute). Ostatní prvky, které obtékají, nejsou prvkem nijak ovlivněny, pouze se jim zkracují řádky v prostoru, kde je obtékaný prvek. Toto chování se ale prohlížeč od prohlížeče liší. Obzvlášť zoufale se chovají různé verze Internet Exploreru.

Pomoci vlastnosti clear se dá říci, že se má prvek vykreslovat až pod všemi obtékanými prvky. Jakmile čemukoliv nastavíte float rozdílné od none, stává se to blokovým prvkem (jakoby display: block).

* Float
    * None - Bez obtékání. Používá se hlavně jako obalový blok.
    * Left - S obtékáním vlevo.
    * Right - S obtékáním vpravo.

#Odkazy

Pro odkazy se používá tag `<a>`. Je to samozřejmě párový tag. Uvnitř tagu se může objevit téměř cokoliv. Klikatelný text či obrázek který nás přesměruje na jinou stránku.

##Atributy odkazu

Atribut | Význam        | Hodnota
--------|---------------|-----------
href    | cíl odkazu    | URL adresa
name	| jméno záložky | libovolné jméno
target  | cílový rám    | _blank (nové okno nebo nový tab); ostatní se nepoužívají
rel     | druh odkazu   | Dnes se používá tak maximálně [nofollow][3] nebo kvůli robotům

Ukázka odkazu:

```html
<a href="http://www.example.com">Ukázka odkazu</a>
```

[1]: images/wa03_tabulka.png
[2]: images/wa03_img.png
[3]: https://support.google.com/webmasters/answer/96569?hl=cs
