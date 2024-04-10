---
title: Les 2
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Maak de structuur van je child theme
{: .text-green-100 .fs-6 }

Je gaat nu de structuur maken van een nieuw child thema zodat je aanpassingen kunt doen zonder het originele thema aan te passen.    

---
### 1- Folder en bestand structuur
1. Maak een nieuwe folder aan
2. Plaats hierin een nieuw bestand met de naam `style.css`
3. Plaats hierin een nieuw bestand met de naam `functions.php`
4. Plaats hierin een nieuw bestand met de naam `screenshot.png`
Meer informatie over child themes: [developer.wordpress.org/themes/advanced-topics/child-themes](https://developer.wordpress.org/themes/advanced-topics/child-themes/)

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
### 4- style.css
In dit bestand geef je aan hoe je thema heet en wat de parent is.  
In dit voorbeeld heb ik een nieuw thema gemaakt met de naam `M8PROG`  
En `cue` _( de folder naam )_ is het parent thema. 
```css
/*
Theme Name: M8PROG
Template: cue
Author: Jasper
*/

```

---
### 5- Controleer
Bekijk de website en zie dat je nu een complete site hebt met een responsive design.

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Stel de style.css in](style_css)

