---
title: Les 3
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Maak de structuur van je custom theme
{: .text-green-100 .fs-6 }

Je gaat nu de structuur maken van een nieuw WordPress thema zodat je een custom website kunt ontwikkelen zonder na hoeft te denken over CRUD-functionaliteit.    

---
### 1- Folder en bestand structuur
1. Maak een nieuwe folder aan met de naam van jouw thema
2. Plaats hierin een nieuw bestand met de naam `style.css`
3. Plaats hierin een nieuw bestand met de naam `functions.php`
4. Plaats hierin een nieuw bestand met de naam `screenshot.png`
Meer informatie over thema's: [https://codex.wordpress.org/Theme_Development](https://codex.wordpress.org/Theme_Development)

---
### 2- screenshot.png
Dit bestand is een screenshot of design van jouw eigen thema zodat je straks makkelijker het thema kunt kiezen.

---
### 3- functions.php
Hier komt diverse functies voor dit thema, bijvoorbeeld om je css te laden:
```php
add_action( 'wp_enqueue_scripts', 'm8prog_enqueue_styles' );

function m8prog_enqueue_styles() {
	wp_enqueue_style(
		'm8prog-style',
		get_stylesheet_uri()
	);
}
```

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Stel de style.css in](style_css)

