---
title: Les 4
layout: page
permalink: :path/:basename
nav_exclude: true
---

## De WordPress pagina structuur
{: .text-green-100 .fs-6 }

**Zorg dat je deze introductie even rustig doorleest zodat je snapt hoe WordPress omgaat met de header en footer.**

---
Binnen een WordPress thema vind je vaak een `header.php` én een `footer.php` document.  
Twee voorbeeld bestanden kun je hier downloaden:  
[header.php](data/header.php)  
[footer.php](data/footer.php)  

Door deze bestanden overal te gebruiken kun je ervoor zorgen dat alle pagina's dezelfde stijl hebben.  
Als je de header van een specifiek post-type anders wilt hebben dan de andere pagina's dan maak je een bestand met een andere naam, bijvoorbeeld: `header-customposttype.php`.  


---
### Header
De header template wordt geladen met het volgende commando: 
```php
<?php
get_header();
?>
```

Binnen de header moet je minimaal deze functie aanroepen in binnen de html `<head>` om diverse functionaliteit uit te voeren zoals het laden van CSS en JavaScripts.  
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
Het idee van de footer is hetzelfde, alleen sluit je nu de footer af.  

---
### Body data
Alle andere informatie wordt straks geladen in onder andere de `index.php`.


---
In de volgende opdracht ga je zelf een `header.php` en `footer.php` maken.
{: .text-blue-100 .fs-4 }

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[WordPress header template en functies](header)


