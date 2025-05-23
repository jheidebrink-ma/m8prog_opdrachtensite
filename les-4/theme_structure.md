---
title: Les 3
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Maak de structuur van je custom theme
{: .text-green-100 .fs-6 }

Veel bedrijven maken een custom WordPress thema voor een specifieke klant of event.  
Jij gaat nu een WordPress thema maken voor een specifieke klant.  
Door gebruik te maken van WordPress hoef je je geen zorgen te maken over CRUD-functionaliteit of database verbindingen.

---
# Thema naam
{: .text-red-100 .fs-6 }
Op de plekken waar je ziet staan: **'M8PROG_THEME_NAME'**  
moet straks natuurlijk naam van jouw eigen thema plaatsen.
{: .text-red-100 .fs-5 }

---
### 1- Structuur van de thema folder
1. Maak een nieuwe folder aan in de thema folder met de naam voor jouw thema, _(gebruik geen kapitalen en spaties)_
2. Plaats hierin een nieuw bestand met de naam `style.css`
3. Plaats hierin een nieuw bestand met de naam `index.php`
4. Plaats hierin een nieuw bestand met de naam `functions.php`
5. Plaats hierin een nieuw bestand met de naam `screenshot.png`
   Meer informatie over thema's: [https://codex.wordpress.org/Theme_Development](https://codex.wordpress.org/Theme_Development)

---
### 2- screenshot.png
Dit bestand is een screenshot of het design van jouw eigen thema zodat je straks makkelijker het thema kunt kiezen.  
Plaats hierin een afbeelding.

---
### 3- functions.php
Hier komt diverse functies voor dit thema net zoals bij het child thema.  
Begin met het laden van de style.
```php
function m8prog_enqueue_styles() {
	wp_enqueue_style(
		'm8prog-style',
		get_stylesheet_uri()
	);
}
add_action( 'wp_enqueue_scripts', 'm8prog_enqueue_styles' );
```
Voeg ook alvast de `featured image` functionaliteit toe zodat je straks eenvoudig afbeeldingen kunt toevoegen aan posts:
```php
add_theme_support( 'post-thumbnails' );
```

---
### 4- index.php
Hier komen straks de codes in die je pagina's weergeven.  
Plaats nu tijdelijk even een voorbeeld tekst in dit document, geen opmaak, alleen een test.   
_Als je niets kunt verzinnen gebruik dan deze dump:_
```php
<?php
echo '<pre style="background:#0f0; padding: 2rem; width:100%;">';
print_r( 'dit is mijn index pagina' );
echo '</pre>';
die(__FILE__.':'.__LINE__);
```

---
### 5- Hiërarchie
De opzet van WordPress gaat volgens een bepaalde structuur, net als bij andere frameworks, meer informatie vind je hier:  
[https://kinsta.com/nl/blog/template-hierarchie-van-wordpress/](https://kinsta.com/nl/blog/template-hierarchie-van-wordpress/)  
Of als je liever een rustgevende video wilt bekijken:  
[https://learn.wordpress.org/tutorial/a-beginners-guide-to-the-wordpress-template-hierarchy/](https://learn.wordpress.org/tutorial/a-beginners-guide-to-the-wordpress-template-hierarchy/)


---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Stel de style.css in](style_css)
