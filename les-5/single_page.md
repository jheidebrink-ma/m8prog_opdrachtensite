---
title: Les 5
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## De WordPress single page
{: .text-green-100 .fs-6 }

Je hebt net een fallback en overzicht pagina gemaakt.  
Nu ga je een pagina maken waarbij je de content van één **page** of **blog post** weergeeft.

---
### 1- Aanmaken van page.php
Dupliceer de `index.php` pagina en noem hem `page.php`  
Deze pagina gaat straks een de informatie van één pagina weergeven.  

---
### 2- Elementen in de page.php
Je hoeft nu niet meer gebruik te maken van een `if statement` of een `loop`.
Je kunt direct in de pagina de verschillende elementen weergeven.  
Het is wel handig om aan het begin van je pagina de onderstaande functie aan te roepen zodat alle data klaar staat om te gebruiken.  
```php
<?php the_post(); ?>
```
Doe je dat niet, dan weet WordPress bij sommige functies niet welke post je bekijkt en krijg je geen of onverwachte data terug.  
**Zorg ervoor dat je de hele content van het bericht weergeeft, niet alleen de intro _( the excerpt )_.**


---
### 3- Single.php
Om de blogs / posts items netjes weer te geven in dezelfde vormgeving kun je nu de `page.php` dupliceren naar `single.php`.  
Voeg een aantal elementen toe die specifiek zijn voor een **blog** item _( nieuws bericht )_.  
Hier kun je verschillende functies vinden die je binnen WordPress kunt gebruiken [https://developer.wordpress.org/reference/functions/](https://developer.wordpress.org/reference/functions/)  
Een paar voorbeelden:
- ```php <?php the_date() ?>``` geeft de datum weer dat het bericht _gemaakt_ is.
- ```php <?php the_modified_date() ?>``` geeft de datum weer dat het bericht _geupdate_ is.
- ```php <?php echo get_avatar( get_the_author_meta('user_email'), '80', '-' ); ?>``` geeft de avatar weer van de auteur.
- ```php <?php the_author_meta('description') ?>``` geeft de bio weer van de auteur.



Wil je ook een volgende en vorige knop om te navigeren tussen de blog posts, dan kun je de onderstaande code gebruiken.  
`Text_Domain` moet je dan vervangen door jouw `Text-Domain` zoals je hebt ingesteld in `style.css`.   
```php
    // Previous/next post navigation.
    the_post_navigation(
        [
            'next_text' => __( 'Next post', 'Text_Domain' ),
            'prev_text' => __( 'Previous post:', 'Text_Domain' ),
        ] 
    );
```


---
### 3- Controleer
Bekijk je website nu in de browser.  
Als het goed is zie je nu de content die je ingesteld hebt in het wp-admin gedeelte.

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
In de volgende opdracht ga je zelf een dynamisch menu implementeren.  
[Menu implementeren](menu)


