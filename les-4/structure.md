---
title: Les 4
layout: page
permalink: :path/:basename
nav_exclude: true
---

## De WordPress pagina structuur
{: .text-green-100 .fs-6 }

**Zorg dat je deze introductie even rustig doorleest zodat je snapt hoe WordPress omgaat met de header en footer.**

![voorbeeld.png](images%2Fvoorbeeld.png)

---
Binnen een WordPress thema vind je vaak een `header.php` én een `footer.php` document.  
Twee **voorbeeld** bestanden kun je hier downloaden:  
[header.php](data/header.php)  
[footer.php](data/footer.php)  
_Dit zijn voorbeeld bestanden ter inspiratie._  
Maak zelf een `header.php` én een `footer.php` bestand aan in je thema folder, hiermee zorg je dat alle pagina's dezelfde stijl hebben.  

Als je de _header_ van een specifiek _post-type_ anders wilt hebben dan de andere pagina's dan maak je een bestand met een andere naam.  
Bijvoorbeeld: `header-customposttype.php`.  


---
### Header
In vorige php projecten gebruikte je `include()`, `require()` of `@import()` functies om een bepaald document in te laden. Binnen WordPress is er voor de header en footer een uitzondering.   
De header template kun je laden met het volgende php commando: 
```php
get_header();
```

Binnen de header.php moet je minimaal de onderstaande php functie aanroepen.  
Deze moet je laden binnen de html `<head>` om diverse functies uit te voeren zoals het laden van CSS en JavaScripts.  
```php
<?php
wp_head();
?>
```

Binnen de header voeg je diverse HTML elementen toe:
- Open de `html` tag
- Open en sluit de `head` tag
- Voeg de `meta tags` toe aan de head 
- Voer binnen de head de php functie `wp_head()` uit 
- Open de body tag en voeg daar de `body_class` aan toe: `<body <?php body_class(); ?>>`
- Implementeer de navigatie.

---
### Footer
Het idee van de footer is hetzelfde als de titel, alleen sluit je nu de html af.  
De footer template wordt geladen met de volgende php functie:
```php
get_footer();
```

Binnen de footer moet je minimaal deze php functie aanroepen net voor je de `body` tag afsluit.  
Deze php functie zorgt ervoor dat er diverse acties uitgevoerd worden zoals het laden van JavaScripts en extra toevoegingen aan de HTML pagina.  
```php
<?php
wp_footer();
?>
```

Binnen de footer voeg je diverse HTML elementen toe:
- Voer net voor het afsluiten van de body de php functie `wp_footer()` uit
- Sluit de `body` tag
- Sluit de `html` tag

---
### Body data
Alle andere informatie zoals een titel, intro, omschrijving worden straks geladen in onder andere de `index.php`.

---
In de volgende opdracht ga je zelf een `header.php` en `footer.php` maken.
{: .text-blue-100 .fs-4 }

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[WordPress header template en functies](header)


