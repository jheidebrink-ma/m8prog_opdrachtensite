---
title: Les 3
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Stel de style.css in
{: .text-green-100 .fs-6 }

In het style.css bestand geef je nu wat informatie over dit thema weer.    

---
### 1- style.css
In dit bestand geef je aan hoe je thema heet en wat de parent is.  
In dit voorbeeld heb ik een nieuw thema gemaakt met de naam `M8PROG_THEME_NAME`  
Zie voor alle opties: [https://developer.wordpress.org/themes/core-concepts/main-stylesheet/](https://developer.wordpress.org/themes/core-concepts/main-stylesheet/)  
{: .mb-0 }
## Dit is een voorbeeld, let op dat je wel de juiste versie van php én WordPress instelt, anders werkt het thema niet.
{: .text-red-100 .fs-4 .mt-2 .mb-4 }

```css
/**
 * Theme Name:        M8PROG_THEME_NAME
 * Theme URI:         https://ma-web.nl
 * Description:       This is a custom WordPress theme
 * Version:           0.0.1
 * Author:            Jasper Heidebrink
 * Author URI:        https://ma-web.nl
 * Tags:              m8prog
 * Text Domain:       M8PROG_THEME_NAME
 * Domain Path:       /languages
 * Tested up to:      6.5
 * Requires at least: 6.4
 * Requires PHP:      8.2
 * License:           GNU General Public License v2.0 or later
 * License URI:       https://www.gnu.org/licenses/gpl-2.0.html
 */

```
Hier kun je zien welke versie van WordPress php je gebruikt:
[/wp-admin/site-health.php?tab=debug](http://localhost:80/wp-admin/site-health.php?tab=debug)  
De items `Text Domain` en `Domain Path` gaan wij later gebruiken voor de vertalingen.


---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Activeer en controleer dit thema](check)

