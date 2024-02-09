---
title: Les 3
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Overview: Wat zijn routes?
{: .text-green-100 .fs-6 }

Het bestand met de *routes*: `routes/web.php` bevat alle routes voor je website.
Het is als het ware de menukaart van je website.

- Voor elke pagina of URL op je website **MOET** je een route definiëren.
- Die routes plaats je in het bestand `routes/web.php`.
- We website kan alleen maar naar routes toe die hier gedefinieerd zijn.


### Wat heb je nodig om een route te laten werken?
1. Een URL (die mag je zelf bedenken, dus verzin een SEO vriendelijke url)
2. Een request method (GET,POST). Meestal gebruik je GET. Voor form afhandeling meestal POST.
3. Een controller class. 
4. Een public function (method) in de class die de code voor jouw route bevat.
5. Een view ( een blade.php bestand in de resources/views ) die de HTML bevat zoals aangegeven in een route of controller.

### Voorbeeld
Hier een voorbeeld hoe je **GET** een route maakt naar de url **/blog** die afgehandeld wordt door de function **index** in een **BlogController**.
De route heeft een (interne naam) *blog.index* (hiermee kun je er makkelijker naar linken in je code).

![Route](images/route-example.png)

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Routes, controllers en views maken voor jouw website](routes-controllers-views)
