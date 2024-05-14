---
title: Les 2
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Maak de structuur van je child theme
{: .text-green-100 .fs-6 }

Je gaat nu de structuur maken van een nieuw child thema zodat je aanpassingen in de code kunt maken zonder het originele thema aan te passen.    

---
### 1- Folder en bestand structuur
1. Maak een nieuwe folder aan in de thema folder, _(gebruik géén kapitalen en géén spaties)_
2. Plaats hierin een nieuw bestand met de naam `style.css`
3. Plaats hierin een nieuw bestand met de naam `functions.php`
4. Plaats hierin een nieuw bestand met de naam `screenshot.png`  
Meer informatie over child themes: [developer.wordpress.org/themes/advanced-topics/child-themes](https://developer.wordpress.org/themes/advanced-topics/child-themes/)

---
### 2- screenshot.png
Dit bestand is een screenshot of het design van jouw eigen thema zodat je straks makkelijker het thema kunt kiezen.  
Plaats hier willekeurige maar wel _Safe For Work_ afbeelding in.

---
### 3- functions.php
Hier komt diverse functies voor dit thema.  

**Action hooks**  
Met action hooks kan je een functionaliteit aanvullen of uitschakelen.  
WordPress heeft vaste momenten dat er een action aangeroepen wordt, daar kun jij met je code op inhaken.  
Bijvoorbeeld als alle plugins geladen zijn, of als de styles geladen moeten worden.  
Zie voor meer informatie: [WP Action Reference](https://developer.wordpress.org/apis/hooks/action-reference/)  

Voor nu kun je jouw css te laden via een action hook.  
```php
function m8prog_enqueue_styles() {
	wp_enqueue_style(
		'm8prog-style',
		get_stylesheet_uri()
	);
}
add_action( 'wp_enqueue_scripts', 'm8prog_enqueue_styles' );
```

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Stel de style.css in](style_css)

