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

Jinak řečeno, DOM je sada funkcí (metod), které umí pracovat s HTML stránkou (např. změnit barvu písma, přidat odstavec atd). Celé to vychází z myšlenky objekově orientovaného programování (OOP), tj. jsou tu objekty, které obsahují metody. K maturitě bychom měli znát tyhle objekty a jejich metody:

#Důležité metody

##[`document.write()`][1]

`document.write()` vypíše text na stránku. Například:

```js
document.write("Ahoj");
document.write("ky");
```

napíše:

> Ahojky

Je taky dobré vědět, že tuto funkci lze takto použít jen dokud se stránka načítá. Pokud spustíme funkci až po tom, co je stránka načtená (např. při kliknutí na nějaké tlačítko či odkaz), vymaže se veškerý obsah, co byl na stránce předtím. Pokud chcete, můžete si to [vyzkoušet][2].

--------------------------

##[`document.getElementsByName()`][3], [`document.getElementsByClassName()`][4] a [`document.getElementById()`][5]

Najde prvek (prvky) na stránce podle jména (např. `xxx` v `<input type="text" name="xxx">`), třídy (atribut `class`) nebo ID. S těmito prvky pak lze dále pracovat. Nejlépe to vysvětlí ukázka:

HTML:

```html
<div id="a">První</div>
<div class="even red">Druhý</div>
<div>Třetí</div>
<div id="d" class="even">Čtvrtý</div>
<div name="last" class="red">Pátý</div>
```

Javascript:

```js
document.getElementById('a').innerHTML = "XXX";
document.getElementById('d').innerHTML = document.getElementsByClassName('even')[0].innerHTML;
```

V tomto případě bude do prvního divu (ten s `id="a"`) napsáno XXX. Poté se načte vnitřek prvního divu se třídou `even` (tj. *Druhý*) a ten přepíše text *Čtvrtý* v divu s `id="d"`.

Složitější příklad (jen JS, HTML kód stejný):

```js
var cervene = document.getElementsByClassName('red');
for (var i = 0; i < cervene.length; i++){
    cervene[i].style.color = "red";
}
```

Tento kód obarví prvky s třídou `red` červeně. Celý příklad si můžete vyzkoušet [zde][6].

###Upozornění:

* Dva stejné prvky na stránce nesmí mít stejné id. *Class* i *name* se opakovat může.
* Kvůli tomu getElementById vrátí jeden konkrétní prvek, ale zbylí dva vrátí pole (array) a je nutné použít hranaté závorky pro přístup ke konkrétnímu prvku, např. `[0]` vrátí 1. nalezený prvek, `[1]` ten druhý atd. **Tohle platí, i kdyby `getElementsByClassName` nebo `getElementsByName` vrátil jenom _jeden_ prvek.** Lze používat i cykly.
* Všiměte si, že _getElement**s**ByClassName_ a _getElement**s**ByName_ obsahují v názvu metody písmeno **`s`**, zatímco _getElementById_ nikoliv.
* Název třídy (class) nebo ID mohou obsahovat čísla, ale **nesmí** s nimi začínat.
* Jeden prvek může mít více tříd, oddělují se mezerami. S `id` nebo `name` tohle nejde.

##window.něco

Slouží k manipulaci s oknem prohlížeče (otevření, zavření, změna velikosti, hejbání s posuvnímem a tak). Snad není třeba vysvětlovat, můžete si je hned zkusit:

<input type="button" value="Otevři okno" onclick="otevri()">
<input type="button" value="Otevři okno 2" onclick="otevri2()">
<input type="button" value="Zavři okno 2" onclick="zavri()">
<input type="button" value="okno2.resizeTo(300, 300)" onclick="okno2.resizeTo(300, 300)">
<input type="button" value="okno2.moveTo(100, 100)" onclick="okno2.moveTo(100, 100)">
<input type="button" value="okno2.focus()" onclick="okno2.focus()">
<input type="button" value="window.scrollTo(0, 1000)" onclick="window.scrollTo(0, 1000)">

<script>
var okno2;

function otevri() {
    window.open("http://www.google.com");
}

function otevri2() {
    okno2 = window.open("vzor", "_blank", "width=500,height=300");
}

function zavri() {
    okno2.close();
}
</script>

Ukázka kódu js prvních 3 tlačítek:

```js
var okno2;

function otevri() {
    window.open("http://www.google.com");
}

function otevri2() {
    okno2 = window.open("http://www.google.com", "_blank", "width=500,height=300");
}

function zavri() {
    okno2.close();
}
```

Pod `window.něco` patří taky alert, prompt a confirm. Asi známte, pokud ne, je to vysvětleno [třeba tady][7].

##Location, History (back, forvard, go)

Pokud neznáte, tyhle dvě tlačítka vám to vysvětlí:

<input type="button" value='location.href="http://www.google.com"' onclick='location.href="http://www.google.com"'>
<input type="button" value='history.back()' onclick='history.back()'>

`history.go()` je něco podobného, jako back/forward, akorát do závorky jako parametr napíšete, o kolik kroků chcete jít dopředu. Třeba tohle:

```js
history.go(-2)
```

vás vrátí v prohlížeči na předminulou stránku. A `history.go(0)` dělá to samé, co `location.reload()`, `location.href = location.href` nebo klávesa F5.

##navigator.appName

Zastaralá vlastnost, která vám měla říct, co uživatel používá za prohlížeč, pokud byste to náhodou někdy chtěli vědět. Ve skutečnosti to ale řekne, že `Netscape`, bez ohledu na to, co uživatel opravdu používá.

##navigator.appVersion

Pokud se chcete k nesmyslnýmu údaji o názvu prohlížeče dozvědět ještě jeho verzi, tak je tady. S největší pravděpodobností se dozvíte, že je `5.0`. Pro větší zmatek za tím může ještě bejt (třeba v závorce) uvedený nějaký doplňujicí údaj, což je úplná blbost, která nemá s verzí prohlížeče nic společného a nikdy vám k ničemu nebude.

##navigator.userAgent

Pokud byste chtěli o tom prohlížeči opravdu něco vědět, tak tohle je vaše jediná možnost. Tahle vlastnost vrací tzv. user-agenta, tj. řetězec, který obsahuje nějaké údaje o prohlížeči a vypadá nějak takto:

    Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:38.0) Gecko/20100101 Firefox/38.0

Nicméně, najít něco v tomto řetězci je celkem umění. Každý prohlížeč vrací něco úplně jiného. A uživatel může prohlížeč přenastavit tak, aby kecal. A některý prohlížeče kecaj samy od sebe.

#Fotogalerie (praktická ukázka)

[Tady (je to jeden soubor, můžete kliknout pravým a stáhnout si ho).][8]

[1]: https://developer.mozilla.org/en-US/docs/Web/API/Document/write
[2]: javascript:document.write('Ahoj')
[3]: https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName
[4]: https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName
[5]: https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById
[6]: http://jsfiddle.net/3bt4bom9/1/
[7]: https://developer.mozilla.org/en-US/docs/Web/API/Window/alert
[8]: download/otazka06.html
