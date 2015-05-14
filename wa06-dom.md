---
title: Document Object Model (DOM)
---

Otázka 6: Document Object Model (DOM)
=====================================

> Zadání
> ------
> 
> Vlastnosti a metody objektů Document (write, getElementsByName, getElementById), Window (open, close, focus, resizeTo, moveTo, scrollTo, alert, confirm, prompt), Location, History (back, forvard, go), Navigator (appName, appVersion, userAgent).
> 
> *Fotogalerie (změna fotografie, změna textu – popisu fotografie, zobrazení a skrytí tlačítek, otevření fotografie do nového okna, přesměrování na JavaScriptovou fotogalerii).*

*DOM je objektově orientovaná reprezentace XML nebo HTML dokumentu. DOM je API umožňující přístup či modifikaci obsahu, struktury, nebo stylu dokumentu, či jeho částí. -- Wikipedie*  
Jinak řečeno, DOM je sada funkcí (metod), které umí pracovat s HTML stránkou (např. změnit barvu písma, přidat odstavec atd). Celé to vychází z myšlenky objekově orientovaného programování (OOP), tj. jsou objekty, které obsahují metody. K maturitě bychom měli znát tyhle objekty a jejich metody:

#Seznam metod, co máme znát

##[`document.write()`][1]

`document.write()` vypíše text na stránku. Například:

```js
document.write("Ahoj");
document.write("ky");
```

napíše:

> Ahojky

Je taky dobré vědět, že tuto funkci lze takto použít jen dokud se stránka načítá. Pokud spustíme funkci až po tom, co je stránka načtená (např. při kliknutí na nějaké tlačítko či odkaz), vymaže se veškerý obsah, co byl na stránce předtím. Pokud chcete, můžete si to [vyzkoušet][2].

-- pokračování příště --

[1]: https://developer.mozilla.org/en-US/docs/Web/API/Document/write
[2]: javascript:document.write('Ahoj')
