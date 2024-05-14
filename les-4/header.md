---
title: Les 4
layout: page
permalink: :path/:basename
nav_exclude: true
---

## WordPress header template en functies 
{: .text-green-100 .fs-6 }

Je gaat nu de `header.php` instellen zodat alle pagina's dezelfde HTML vormgeving en functionaliteit hebben.  
_De vormgeving zal minimaal zijn, volgende les gaan we daar mee aan de slag._ 

---
### 1- Header document aanmaken
Maak een nieuw document in je thema folder en met de naam:  
`header.php`

---
### 2- Header implementeren in de index.php
In de `index.php` moet je nu boven in het bestand _( op regel 1 )_ de header importeren.  
Doe dit door de php functie te gebruiken zoals je op de vorige pagina hebt gelezen.  

---
### 3- Header.php instellen
Zorg er nu voor dat je net zoals in het `header.php` voorbeeld een HTML pagina opent.  
De volgende `tags` moet je minimaal in dit document plaatsen, afsluiten van de `html` en `body` doe je in de footer.  
Maar mogelijk moet je ook een titel toevoegen.  
```php
<!doctype html>
<html <?php language_attributes() ?>>
<head>
	<meta charset="<?php bloginfo( 'charset' ) ?>" />
	<?php wp_head() ?>
</head>

<body <?php body_class() ?>>
<?php wp_body_open() ?>
```

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[WordPress footer template en functies](footer)


