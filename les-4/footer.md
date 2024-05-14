---
title: Les 4
layout: page
permalink: :path/:basename
nav_exclude: true
---

## WordPress footer template en functies 
{: .text-green-100 .fs-6 }

Je gaat nu de `footer.php` instellen zodat alle pagina's dezelfde HTML vormgeving en functionaliteit hebben.

---
### 1- Footer document aanmaken
Maak een nieuw document in je thema folder en met de naam:  
`footer.php`

---
### 2- Footer implementeren in de index.php
In de `index.php` moet je nu de footer importeren onderaan het bestand.  
Doe dit door de php functie te gebruiken zoals je op de introductie pagina hebt gelezen.

---
### 3- Footer.php instellen
- Zorg er nu voor dat je de `<body>` en `<html>` tags afsluit in de `footer.php`.  
- Plaats boven het afsluiten van de `body` de volgende code: `<?php wp_footer() ?>`
- Voeg een tekstje toe zodat je straks weet waar de footer op je pagina verschijnt.  

---

Het resultaat van je website ziet er nu mogelijk zo uit:
![voorbeeld.png](images%2Fvoorbeeld.png)

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[HTML structuur](html)
