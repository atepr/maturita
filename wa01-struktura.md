---
title: Struktura HTML dokumentu
---

Otázka 1: Struktura HTML dokumentu
==================================

> Zadání
> ------
> 
> **Struktura html dokumentu**  
> Typ html dokumentu – html a xhtml, hlavička a tělo, hlavička – znaková sada, připojení css, meta informace, tělo – párové a nepárové tagy, atributy, formátování pomocí css.
> 
> **Textové prvky html stránky**  
> Nadpisy, odstavce, seznamy, vnořené seznamy. Příklady formátování pomocí css.

Ukázka struktury v kódu:

```html
<!DOCTYPE html>
<!-- Komentář -->
<html>
<head>
    <meta charset="UTF-8">
    <title>Titulek</title>
</head>
<body>
   Obsah stránky.
</body>
</html>
```

Ukázka struktury na obrázku:

![Obrázek][1]

--------------------------------------------------------------------------------------------------

    <!DOCTYPE>

Doctype není ve skutečnosti tag, protože je nepárový a není uzavřený. Umožňuje nastavit typ dokumentu a měl by být prvním elementem vaší webové stránky. Dříve byl jeho zápis poněkud složity, nyní jeho zápis vypadá takto: `<!DOCTYPE html>`

--------------------------------------------------------------------------------------------------

    <html>

`<html>` tag obaluje celý HTML dokument, který je dále rozdělen na hlavičku (ta obsahuje informace hlavně pro prohlížeč) a tělo, kde je uložen fyzický obsah dokumentu.

--------------------------------------------------------------------------------------------------

    <head>

Hlavička je první částí HTML dokumentu a obsahuje informace hlavně pro prohlížeč. Povinný je párový tag `<title>`, který specifikuje titulek stránky. Ten se zobrazí na záložce prohlížeče a také se jím řídí vyhledávače. V hlavičce se mohou nacházet i další tagy, jako jsou: `<style>`, `<link>`, `<meta>`, `<script>`, `<noscript>` a `<base>`.

--------------------------------------------------------------------------------------------------

    <title>

`<title>` je párový tag a obsahuje titulek stránky. Každá HTML stránka ho musí v hlavičce obsahovat a je velmi důležitý pro vyhledávače z hlediska SEO. Titulek by měl obsahovat klíčová slova a zobrazí se jako nadpis záložky v prohlížeči.

--------------------------------------------------------------------------------------------------

    <style>

Element `<style>` slouží k vložení stylování přímo do HTML dokumentu. Příliš se nevyužívá, jelikož se styly preferují v externím souboru.

U elementu můžeme uvést nasledující atributy:

* **`type`** - Specifikuje typ stylu, jako hodnotu uvedeme text/css.
* **`media`** - Sepecifikuje typ zařízení pro který je styl optimalizován. Atributem se nyní nebudeme zabývat.
* **`scoped`** - Pokud je atribut uveden, může tag stát mimo hlavičku. Styluje div, jehož id je hodnotou tohoto atributu. Element style je poté součástí tohoto divu.

Ukázka stylu, kde jsou definované styly pro nadpis h1:

```html
<style>
    h1 {
        color: #000000;
        font-size: 25px;
    }
</style>
```

--------------------------------------------------------------------------------------------------

    <link>

`<style>` se používá k provázání dokumentu s externím souborem. Nejčastěji se tak k dokumentu připojují CSS styly. Smí být obsažen pouze v hlavičce a to i několikrát. Nemá obsah, má pouze atributy.

U elementu můžeme uvést nasledující atributy:

* **`href`** - Specifikuje umístění připojovaného souboru (dokumentu).
* **`hreflang`** - Specifikuje jazyk připojovaného dokumentu.
* **`media`** - Specifikuje typ zařízení, pro které je připojovaný dokument určen.
* **`rel`** - Specifikuje vztah mezi dokumenty. nejčastějši hodnoty jsou stylesheet a icon.
* **`sizes`** - Umožňuje specifikovat velikost ikony (pouze pro `rel="icon"`).
* **`type`** - MIME typ připojovaného souboru (dokumentu). Nejčastěji `text/css`.

Ukázka připojení externího CSS stylu a ikonky zvané favicon:

```html
<link rel="stylesheet" type="text/css" href="nazev-souboru.css">
<link rel="icon" href="favicon.ico">
```

--------------------------------------------------------------------------------------------------

    <meta>

Tag `<meta>` poskytuje tzv. metadata. Jedná se o informace vložené do HTML dokumentu, které se nezobrazí uživateli, ale jsou určeny zejména vyhledávačům. Jistě si domyslíte, že jsou důležité pro SEO optimalizaci stránky. Tag musí být vždy umístěn v hlavičce stránky. Kromě vyhledávačů ho používají i webové prohlížeče a webové služby.

Tag má nasledující atributy:

* **`charset`** - Specifikuje znakovou sadu dokumentu. Nejčasteji obsahuje hodnotu UTF-8. Jedná se o nový HTML 5 atribut, který zjednodušuje minulou specifikaci znakové sady.
* **`content`** - Specifikuje parametr pro atributy name a http-equiv.
* **`name`** - Specifikuje jméno metadat, viz. ukázky níže.
* **`http-equiv`** - Umožňuje simulovat hlavičku http odpovědi. Dříve se používal k nastavení kódování. v níže uvedeném obrázku napřiklad obnovujeme dokument každých 30 vteřin (poslední meta tag)

Ukázka Tagů meta:

```html
<!-- Můžeme určit autora webové stránky: -->
<meta name="author" content="Dominik Víšek">
<!-- Dále můžeme předat klíčová slova, kterých se obsah webu týká: -->
<meta name="keywords" content="maturita, otázky, vypracování">
<!-- Nebo vložit popis stránky pro vyhledávače: -->
<meta name="description" content="Maturitní otázky">
<!-- Ale lze nastavit třeba i automatické obnovení stránky: -->
<meta name="refresh" content="30">
```

-----------------------------------------------------------------------------------------------------------

    <script>

`<script>` slouží k vložení klientského skriptu do HTML dokumentu. Nejčastěji se jedná o JavaScript. Tag slouží jak pro přímé vložení kódu, tak pro odkázání na externí soubor s kódem. Druhé použití je častější, preferuje se totiž nemíchat HTML s dalšími jazyky. `<script>` je párový tag.

Tag má nasledující atributy:

* **`async`** - Spustí skript asynchonně a jeho běh tedy nenaruší parsování stránky. Funguje pouze pro externí skripty. Atribut je typu boolean, stačí ho tedy uvést a na hodnotě nezáleží.
* **`defer`** - Skript je spuštěn až po dokončení parsování stránky. Atribut je též typu boolean.
* **`type`** - Obsahuje MIME typ skriptu. Nejčastěji se používá hodnota text/javascript.
* **`charset`** - Specifikuje znakovou sadu uvnitř skriptu.
* **`src`** - Specifikuje umístění externího skriptu. Pokud je atribut uveden, musí být obsah tagu < script> prázdný.

Ukázka tagů script:

--dodělat--

[1]: images/wa01_1.png
