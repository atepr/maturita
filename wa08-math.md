---
title: Objekty Math, String, Date
---

Otázka 7: Objekty Math, String, Date
====================================

> Zadání
> ------
> 
> Metody objektů Math (floor, ceil, round, random), String (length, charAt, toLowerCase, toUpperCase, indexOf, lastIndexOf, substr, substring, split, replace), Date (vytvoření objektu datum, toLocaleString, getDate, getMonth, getFullYear, getDay, getHours, getMinutes, getSeconds, getTime, metody set)
> 
> *Aktuální datum a čas v různém formátu, obrázek podle aktuálního měsíce, náhodně vybraný obrázek (názvy obrázků mohou být uloženy v poli nebo tvořeny několikaciferným číslem), výpis názvu souboru bez přípony, případně bez čísla, malými písmeny, apod. , náhodný číselný nebo písmenný kód*

Názvy jednotlivých metod v Aj jsou asi výstižné a většina funkcí bude použita v příkladech:

##Aktuální datum a čas v různém formátu

```js
var datum = new Date();
var zformatovaneDatum = datum.getDate() + "." + datum.getMonth() + "." + datum.getFullYear();
document.write(zformatovaneDatum);
```

Výsledek:

<blockquote>
<script>
var datum = new Date();
var zformatovaneDatum = datum.getDate() + "." + datum.getMonth() + "." + datum.getFullYear();
document.write(zformatovaneDatum);
</script>
</blockquote>
