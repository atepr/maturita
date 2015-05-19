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
var zformatovaneDatum = datum.getDate() + "." + (datum.getMonth() + 1) + "." + datum.getFullYear();
document.write(zformatovaneDatum);
```

Výsledek:

<blockquote>
<script>
var datum = new Date();
var zformatovaneDatum = datum.getDate() + "." + (datum.getMonth() + 1) + "." + datum.getFullYear();
document.write(zformatovaneDatum);
</script>
</blockquote>

##Obrázek podle aktuálního měsíce

```html
<img src="null.png" alt="Obrázek podle měsíce" id=obr>
<script>
    var datum = new Date();
    var mesic = datum.getMonth() + 1;
    var url = "http://lorempixel.com/100/75/business/" + mesic; // Opravdu nebudu schánět obrázek ke každýmu měsíci
    document.getElementById("obr").src = url;
</script>
```

Výsledek:

<blockquote>
<img src="null.png" alt="Obrázek podle měsíce" id=obr>
<script>
    var datum = new Date();
    var mesic = datum.getMonth() + 1;
    var url = "http://lorempixel.com/100/75/business/" + mesic; // Opravdu nebudu schánět obrázek ke každýmu měsíci
    document.getElementById("obr").src = url;
</script>
</blockquote>

##Náhodně vybraný obrázek (názvy obrázků jsou uloženy v poli)

```html
<img src="null.png" alt="Náhodný obrázek" id=obr>
<script>
    // Adresa obrázku je: http://lorempixel.com/400/200/xxxxx/1/
    // kde xxxxx může být animals, cats, food nebo transport
    
    var moznosti = ["animals", "cats", "food", "transport"];
    var vybranaMozn = Math.floor(moznosti.length * Math.random()); // Vygeneruje číslo možnosti (od 0 do 3)
    var url = "http://lorempixel.com/100/75/" + moznosti[vybranaMozn] + "/1";
    document.getElementById("obr").src = url;
</script>
```

Výsledek:

<blockquote>
<img src="null.png" alt="Obrázek podle měsíce" id=obr>
<script>
    var moznosti = ["animals", "cats", "food", "transport"];
    var vybranaMozn = Math.floor(moznosti.length * Math.random()); // Vygeneruje číslo možnosti (od 0 do 3)
    var url = "http://lorempixel.com/100/75/" + moznosti[vybranaMozn] + "/1";
    document.getElementById("obr").src = url;
</script>
</blockquote>

##Náhodně vybraný obrázek (názvy obrázku je číslo)

```html
<img src="null.png" alt="Náhodný obrázek" id=obr>
<script>
    // Adresa obrázku je: http://sokol-nasavrky.8u.cz/fotogalerie/alba/27/ikony/140405_xxxxx_detsky_turnaj_bad.jpg
    // kde xxxxx může být libovolné číslo od 01 do 30.
    
    var POCET_FOTEK = 30;
    var vybranaMozn = 1 + Math.floor(POCET_FOTEK * Math.random()); // Vygeneruje číslo možnosti (od 1 do 30)

    // Pokud je to třeba, přidá se nula na začátek:
    if (vybranaMozn < 10)
        vybranaMozn = "0" + vybranaMozn;
    
    var url = "http://sokol-nasavrky.8u.cz/fotogalerie/alba/27/ikony/140405_" + moznosti[vybranaMozn] + "_detsky_turnaj_bad.jpg";
    document.getElementById("obr").src = url;
</script>
```

Výsledek:

<blockquote>
<img src="null.png" alt="Obrázek podle měsíce" id=obr>
<script>
    var POCET_FOTEK = 30;
    var vybranaMozn = 1 + Math.floor(POCET_FOTEK * Math.random()); // Vygeneruje číslo možnosti (od 1 do 30)

    if (vybranaMozn < 10)
        vybranaMozn = "0" + vybranaMozn;
    
    var url = "http://sokol-nasavrky.8u.cz/fotogalerie/alba/27/ikony/140405_" + moznosti[vybranaMozn] + "_detsky_turnaj_bad.jpg";
    document.getElementById("obr").src = url;
</script>
</blockquote>
