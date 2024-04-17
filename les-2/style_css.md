---
title: Les 2
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Stel de style.css in
{: .text-green-100 .fs-6 }

In het style.css bestand kun je aangeven hoe het thema heet en wie hem gemaakt heeft.    

---
### 1- style.css
In dit bestand geef je aan hoe je thema heet en wat de parent is.  
In dit voorbeeld heb ik een nieuw thema gemaakt met de naam `M8PROG`  
Het thema `cue` _( de folder naam )_ is het parent thema.
Zie voor alle opties: [https://developer.wordpress.org/themes/core-concepts/main-stylesheet/](https://developer.wordpress.org/themes/core-concepts/main-stylesheet/)
Dit zijn de minimale instellingen 
```css
/*
Theme Name: M8PROG
Template: cue
Author: Jasper
*/

```

Een overzicht van wat meer instellingen:  
Bekijk de instellingen maar eens om te zien wat je zelf wilt gebruiken.  
```css
/**
 * Theme Name:        M8PROG Child theme
 * Theme URI:         https://ma-web.nl
 * Description:       This is a custom child theme
 * Version:           1.0.0
 * Template:          cue
 * Author:            Jasper Heidebrink
 * Author URI:        https://ma-web.nl
 * Tags:              m8prog
 * Text Domain:       m8prog
 * Domain Path:       /languages
 * Tested up to:      6.4
 * Requires at least: 6.2
 * Requires PHP:      7.4
 * License:           GNU General Public License v2.0 or later
 * License URI:       https://www.gnu.org/licenses/gpl-2.0.html
 */
```


---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Activeer en controleer dit thema](check)

