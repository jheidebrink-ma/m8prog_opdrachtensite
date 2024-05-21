---
title: Les 5
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## De WordPress loop structuur
{: .text-green-100 .fs-6 }

**Zorg dat je deze introductie even rustig doorleest zodat je snapt hoe WordPress omgaat met de header en footer.**


---
## Templates
WordPress gebruikt zeven hoofdtypes pagina's, de flow kun je in de afbeelding hieronder zien.  
In deze sectie bespreken lopen wij er even doorheen, in de volgende les gaan wij aan de slag met de index (frond end ).  
Dit zijn de verschillenden pagina types:
1. Frontpagina
2. Single Posts 
3. Single Pages 
4. Custom Post Types 
5. Zoekresultaat pagina's 
6. Categorie, taxonomy- en tag pagina's 
7. 404 error pagina's


![template-cheatsheet.png](images%2Ftemplate-cheatsheet.png)

### 1- Frontpagina
Je WordPress homepagina is vaak de eerste plek die gebruikers zien als zij je website bezoeken.  
Voordat de juiste pagina geladen is zal WordPress in de volgende volgorde zoeken naar deze drie templatebestanden:
1. front-page.php 
2. home.php 
3. index.php
Als je thema geen `front-page.php` templatebestand heeft, gebruikt WordPress standaard de tweede optie, enzovoort.  
Het `index.php` bestand de laatste stop die WordPress maakt in deze beslissingsboom van templates waardoor dit altijd de default is.

### 2- Single Posts
Individuele WordPress artikelen gebruiken de single post.  
Voor elk blogbericht zoekt WordPress naar de volgende bestanden:  
1. single.php 
2. singular.php 
3. index.php
Als je naar het lijstje kijkt over de templates, zal je echter zien dat in sommige gevallen er een complexere hiërarchie is.  
Dat komt omdat je met WordPress aparte template bestanden kan toewijzen voor de verschillende individuele berichten en single categorieën, en het pas op single.php overstapt als het geen van deze opties vindt.

### 3- Single Pages
Na de index zijn voor de meeste WordPress sites ook single pagina's enorm belangrijk.  
In de meeste gevallen is dit een andere template dan de homepagina.  
Zo ziet de hiërarchie van de template van een single page eruit:
1. page.php 
2. singular.php 
3. index.php
Hoewel de template hiërarchie voor **single berichten** en **pagina's** vergelijkbaar is, zijn er enkele belangrijke verschillen, de belangrijkste:  
Je kunt ook de template maken voor specifieke _slugs_ en _ID's_.  
Als je een `page-{slug}.php` of een `page-{id}.php` bestand hebt zal WordPress deze eerder laden dan de standaard `page.php`.

### 4-  Custom Post Types
Je kan custom post-types maken om een specifiek type content aan te geven.  
Custom post-types zorgen voor betere organisatie van je content en hebben ook hun eigen template-hiërarchie:
**Voor de overzicht pagina's:**
1. archive-{post_type}.php 
2. archive.php 
3. index.php
**Voor de enkele pagina's**
1. single-{post_type}.php 
2. single.php 
3. singular.php 
4. index.php
De template-hiërarchie voor custom berichttypes is minder complex dan volledige pagina’s of berichten.  
Met WordPress kun je template bestanden maken voor elk custom berichttype, omdat ze niet exact dezelfde lay-outs hoeven te delen.

### 5- Zoekresultaat pagina’s
Binnen WordPress is er een standaard pagina die zoekresultaten weergeeft.  
Zo ziet de hiërarchie van de template van een zoek page eruit:
1. search.php 
2. index.php
Binnen een zoekpagina hoef je waarschijnlijk niet veel elementen op te nemen behalve de resultaten zelf.  

### 6- Categorie-, taxonomie- en tagpagina's  
Hoewel veel websites er niet rechtstreeks naar linken, genereert WordPress collectieve pagina's voor je tags, taxonomies en categorieën.  
Er zijn ook specifieke subpagina’s voor elk item binnen die taxonomie.
Doordat de taxonomie erg complex kan worden voor websites met veel content, omvat deze hiërarchie meer ‘stappen’ dan normaal:
1. category–{slug}.php 
2. category-{id}.php 
3. category.php 
4. archive.php 
5. index.php
Categorieën, taxonomies en tags worden op dezelfde manier verwerkt in WordPress.  
In de bovenstaande structuur vervang je voor alleen `category` door `tag` of `taxonomy`.

## 7- 404 error pagina’s
Soms proberen bezoekers toegang te krijgen tot een pagina die niet bestaat.  
Wanneer dat gebeurt retourneert WordPress net als bij andere websites een `404 error pagina`.  
Standaard biedt WordPress geen mogelijkheden om het uiterlijk van deze pagina aan te passen zodat deze mooi in stijl is van je website.  
De template-hiërarchie is vrij kort:
1. 404.php 
2. index.php
Zo kun je bijvoorbeeld ook een zoekformulier toevoegen aan de 404 pagina om bezoekers te helpen de juiste pagina te vinden.  

---
## Dit was even een flink verhaal, maar het is de basis van WordPress dus erg belangrijk dat je de flow snapt.
{: .text-green-100 .fs-5 } 

---
### Links
- [Meer informatie over de hiërarchie](https://developer.wordpress.org/themes/basics/template-hierarchy/)

---
### Volgende stap:
{: .text-green-100 .fs-4 }   
[WordPress loop implementeren in de index](index_loop)


