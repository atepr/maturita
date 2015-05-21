---
title: Události JavaScriptu, regulární výrazy
---

Otázka 9: Události JavaScriptu, regulární výrazy
====================================

> Zadání
> ------
> 
> Druhy událostí (onclick, ondblclick, onmouseover, onmouseout, onchange, onload, onfocus, onblur, onsubmit, onreset, onkeypress), způsob jejich obsluhy, příklady použití.  
> Zápis regulárních výrazů JavaScriptu, metoda test. Příklady použití regulárních výrazů.
> 
> *Kontrola dat formuláře při odeslání, průběžná kontrola při vyplňování polí.*

Události
--------

JavaScript podporuje tzv. události (events), které zavolají kus kódu, když se něco stane *(např. načtení stránky, kliknutí na něco, najetí myší, vyplnění furmuláře atd.).* Existují dva způsoby zápisu událostí. Ten první se už dnes nepoužívá a funguje tak, že se k HTML tagu dá atribut, který začíná na `on` a pak následuje jméno události, například:

```html
<a href="#" onclick="alert('Někdo na mě kliknul')">Klikni sem</a>
```

Výsledek:

> <a href="#" onclick="alert('Někdo na mě kliknul')">Klikni sem</a>

Druhý a lepší způsob je použít posluchač (listener). Je výhoda spočívá v oddělení JavaScriptu od HTML. Ale neučili jsme se ho, takže ho nejspíše znát nemusíte. Nicméně je to stejný, jak jsme se to učili ve Flashi. JavaScript umí tyto události:

Událost         | Vysvětlení
----------------|--------------------------------------------------------
onclick         | Kliknutí myší na prvek
ondblclick      | Dvojklik
onmouseover     | Najetí myší
onmouseout      | Odjetí myší (tj. nejdříve na něco myší najedete a pak z toho odjedete pryč).<br>*Obvykle slouží ke zrušení akce, co se provedla při onmouseover.*
onchange        | Po změně hodnoty poli ve formuláři<br>*U textového pole se zavolá až když dopíšete text a kliknete z formuláře pryč, ne v průběhu psaní.*
onload          | Po načtení. Lze použít u `<body>` nebo `<img>`
onfocus         | Když textové pole získá *fokus* (kliknete na něj, že budete psát nebo se k němu dostanete přes tab).
onblur          | Ztráta *focusu*. Podobný vztah jako mezi *onmouseover* a *onmouseout*.
onsubmit        | Odeslání formuláře (buďto kliknutím na odesílací tlačítko nebo i entrem).
onreset         | Kliknutí na resetovací tlačítko (`<input type=reset>`)
onkeypress      | Při vyplňování texového pole ve formuláři. Na rozdíl od `onchange` se zavolá po každém napsaném písmenu.

Regulární výrazy
----------------

Nejdříve pár slov k tomu, co je to regulární výraz. Regulární výraz je věc, pomocí které se kontroluje, zda řetězec odpovídá zavanému formátu. Lze takto ověřit například telefoní číslo *(devět čísel za sebou → `^[0-9]{9}$`)*, e-mailovou adresu *(něco, zavináč, něco, tečka a znovu něco → `.+@.+\..+`)* či datum narození *(číslo nebo dvě, tečka, to celé dvakrát a 4 čísla → `^([0-9]{1,2}\.){2}[0-9]{4}$`)*. Na druhou stranu regulární výrazy nejdou dokonalé, třeba nepoznají, jestli ten e-mail skutečně existuje nebo jestli se ten člověk skutečně narodil v daný den. A nejen to, ani nepozají, když někdo napíše, že se narodil *30.15.2015*, budou to brát jako platné datum narození. Upravit tenhle výraz tak, aby to rozpoznal, je docela velký problém, pokud to vůbec je možné. Pokud si chcete nějaké výrazy vyzkoušet, můžu doporučit třeba [tuhle stránku][1].

V JavaScriptu se regulární výraz chová jako objekt. Lze ho vytvořit literálem nebo konstruktorem. Například regexp `^[a-z]+$` lze vytvořit jako:

```js
var vyraz = /^[a-z]+$/i;
var vyraz = new RegExp("^[a-z]+$", "i");
```

Poté ho lze použít buďto ke kontrole vstupních dat nebo k hledání v řetězci (+ případně nahrazení). Ukázka ověření, textu pomocí výrazu výše:

```js
if (vyraz.test("Ahoj")){
    document.write("Ahoj <b>odpovídá</b> výrazu /^[a-z]+$/i");
}
else{
    document.write("Ahoj <b>neodpovídá</b> výrazu /^[a-z]+$/i");
}
```

Výsledek:

> Ahoj <b>odpovídá</b> výrazu /^[a-z]+$/i

**Poznámka:** volba `i` (za lomítkem) znamená, že se nebudou rozlišovat velká a malá písmena.

Příklad (kontrola formuláře)
----------------------------

HTML:

```html
<form action="" onsubmit="return overFormular()">
    <div><label>Datum:</label><input name="datum" type="text"></div>
    <div><label>Počet vstupenek:</label><input name="pocet" type="number" min="1"></div>
    <div><input type="submit" value="Odeslat"></div>
</form>
```

Javascript:

```js
function overFormular(){
    var datum = document.getElementsByName("datum")[0].value;
    var pocet = document.getElementsByName("pocet")[0].value;
    if (!(datum.match(/^\d{1,2}\.\d{1,2}\.\d{4}$/) && pocet > 0)){
        alert ("Vyplň to dobře.");
        return false;
    }
    return true;
}
```

Ukázka:

<blockquote>
<form action="" onsubmit="return overFormular()">
   <div><label>Datum:</label><input name="datum" type="text"></div>
   <div><label>Počet vstupenek:</label><input name="pocet" type="number" min="1"></div>
   <div><input type="submit" value="Odeslat"></div>
</form>
<script>
function overFormular(){
    var datum = document.getElementsByName("datum")[0].value;
    var pocet = document.getElementsByName("pocet")[0].value;
    if (!(datum.match(/^\d{1,2}\.\d{1,2}\.\d{4}$/) && pocet > 0)){
        alert ("Vyplň to dobře.");
        return false;
    }
    return true;
}
</script>
</blockquote>

[1]: http://www.regexp.cz/index.php
