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

---

    <!DOCTYPE>

Doctype není ve skutečnosti tag, protože je nepárový a není uzavřený. Umožňuje nastavit typ dokumentu a měl by být prvním elementem vaší webové stránky. Dříve byl jeho zápis poněkud složity, nyní jeho zápis vypadá takto: `<!DOCTYPE html>`

---

    <html>

`<html>` tag obaluje celý HTML dokument, který je dále rozdělen na hlavičku (ta obsahuje informace hlavně pro prohlížeč) a tělo, kde je uložen fyzický obsah dokumentu.

---

    <head>

Hlavička je první částí HTML dokumentu a obsahuje informace hlavně pro prohlížeč. Povinný je párový tag `<title>`, který specifikuje titulek stránky. Ten se zobrazí na záložce prohlížeče a také se jím řídí vyhledávače. V hlavičce se mohou nacházet i další tagy, jako jsou: `<style>`, `<link>`, `<meta>`, `<script>`, `<noscript>` a `<base>`.

---

    <title>

`<title>` je párový tag a obsahuje titulek stránky. Každá HTML stránka ho musí v hlavičce obsahovat a je velmi důležitý pro vyhledávače z hlediska SEO. Titulek by měl obsahovat klíčová slova a zobrazí se jako nadpis záložky v prohlížeči.

---

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

---

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
--- napsat kód ---
```

-- dodělat --

[1]: images/wa01_1.png
