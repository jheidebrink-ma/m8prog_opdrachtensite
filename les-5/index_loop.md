---
title: Les 5
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## De WordPress loop in de index
{: .text-green-100 .fs-6 }

Wij gaan nu de dynamische content in de pagina plaatsen.  
In het wp-admin gedeelte heb je al wat data toegevoegd, deze gaan wij nu aan de voorkant laten zien.

---
### Voorbereiding
{: .text-red-500 .fs-5 }
Voordat voordat je de informatie kunt weergeven moet je eerst twee extra blog posts aanmaken, dit heb je nodig om straks te kunnen testen.  
### 1- Posts aanmaken
{: .text-green-500 .fs-3 }
Ga in het **wp-admin** gedeelte naar `posts` toe, en voeg een nieuwe post toe.   
_Vergeet niet om op `publish` te klikken._  
_Maak minimaal 2 posts aan._  
### 2- Pagina aanmaken
{: .text-green-500 .fs-3 }
Vervolgens maak je een **page** _( pagina )_ die je gebruikt om de posts / je blog te kunnen zien.  
Voer in deze pagina alleen een titel toe, bijvoorbeeld **blog**, verder mag hij leeg zijn.  
Doe dit door onder **pages** te klikken op **new**  
### 3- Posts pagina selecteren
{: .text-green-500 .fs-3 }
Ga naar de instellingen / settings  
Selecteer hier `reading`  
Selecteer onder de optie `Posts page` jouw net aangemaakte **blog pagina**  
Als je nu in je nu in je browser naar deze blog pagina toe gaat dan zie je nog niet een overzicht van de berichten, dat klopt!   
Je bent nu klaar om aan deze les te beginnen.  

---
### 1- De header
Het is wel zo netjes als in de titel van de pagina ook de naam van de pagina en de site titel staat.  
Pas daarom de `<title>` tag aan in de `header.php`  
De titel van de **pagina** laat je zien door deze code te gebruiken:
```php
<?php the_title() ?>
```
De titel van de **site** haal je op deze manier op:
```php
<?php bloginfo('title') ?>
```

---
### 2- De index.php
In de `index.php` zie je straks mogelijk meerdere berichten onder elkaar staan.  
Daarom is het belangrijk om in de `index.php` pagina een loop te plaatsen.  
Wij gaan gebruik maken van een `while loop`.  
Eerst controleren wij of er wel een post is door te controleren op de volgende waarde:
```php
have_posts()
```
Als de pagina minimaal **één** post heeft voer je de **loop** uit, anders geef je een melding dat er geen data is gevonden.  
Dat kun je uitproberen door een pagina aan te roepen die niet bestaat zoals: [/ik_ben_er_niet](http://localhost/ik_ben_er_niet)

Nu moet je een **while loop** maken binnen deze **if statement**, voer deze loop uit zolang `have_posts()` **true** terug geeft.

Zodra je de while loop opent is het belangrijk om eerst de post informatie op te halen zodat je verderop de juiste data weergeeft.  
Hiervoor gebruik je dit commando: 
```php
the_post();
```

Daarna kun je verschillende onderdelen van de post ophalen én weergeven met commando's zoals: `the_title()`, `the_excerpt()` en `the_content()` 

Alles bij elkaar zal je code er ongeveer zo uit zien.  
```php
// Start with a if statement
if ( have_posts() ) :

	// Loop trough the posts
	while ( have_posts() ) :
	    // Load the data post data
		the_post();
		?>
        <main class="container my-5">
            <h1 class="mt-5"><?php the_title() ?></h1>
            <div class="col-lg-8 px-0">
                <?php the_excerpt() ?>
            </div>
        </main>
	    <?php
	endwhile;

else: 
    echo 'Volgens mij zoek je iets dat er niet is';
endif;
```


---
### 3- Controleer
Bekijk je website nu in de browser.  
Als het goed is zie je nu de content / data die je een vorige les hebt ingevoerd in het **wp-admin** gedeelte.  
Dit was toen waarschijnlijk een pagina of een blog post.

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
In de volgende pagina ga je één enkele pagina of blog item weergeven.  
[Single page en blog implementatie](single_page)


