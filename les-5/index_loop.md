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
## 1- De header
Het is wel zo netjes als in de titel van de pagina ook de naam van de pagina en de site titel staat.  
Pas daarom de `<title>` tag aan in de `header.php`
De titel van de pagina laat je zien door deze code te gebruiken:
```php
<?php the_title() ?>
```
De titel van de site haal je op deze manier op:
```php
<?php bloginfo('title')?>
```

---
## 2- De index.php
In de `index.php` zie je straks mogelijk meerdere berichten onder elkaar staan.  
Daarom is het belangrijk om in de `index.php` pagina een loop te plaatsen.  
Wij gaan gebruik maken van een `while loop`.  
Eerst controleren wij of er wel een post is door te controleren op de volgende waarde:
```php
have_posts()
```
Als de pagina posts heeft voer je de loop uit, anders geef je een melding dat er geen data is gevonden.  
Dat kun je uitproberen door een pagina aan te roepen die niet bestaat zoals: [/ik_ben_er_niet](http://localhost/ik_ben_er_niet)

Nu moet je een **while loop** maken binnen deze **if statement**, voer deze loop uit zolang `have_posts()` `true` is.

Zodra je de while loop opent is het belangrijk om eerst de post informatie op te halen zodat je verderop de juiste data weergeeft.  
Hiervoor gebruik je dit commando: 
```php
the_post();
```

Alles bij elkaar zal je code er ongeveer zo uit zien.  
```php
// Start the loop.
if ( have_posts() ) :

	// Load posts loop.
	while ( have_posts() ) :
	    // load the data
		the_post();
		?>
        <main class="container my-5">
            <h1 class="mt-5"><?php the_title() ?></h1>
            <div class="col-lg-8 px-0">
                <?php the_content() ?>
            </div>
        </main>
	    <?php
	endwhile;

else: 
    echo 'Volgens mij zoek je iets dat er niet is';
endif;
```


---
### Links
- [Meer informatie over de hiërarchie](https://developer.wordpress.org/themes/basics/template-hierarchy/)

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
In de volgende opdracht ga je zelf een `loop` maken.  
[WordPress Loop uin de index](index_loop)


