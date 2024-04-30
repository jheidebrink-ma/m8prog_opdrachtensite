---
title: Les 7
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Weergeven van custom post types
{: .text-green-100 .fs-6 }

Uiteindelijk is het doel om deze items weer te geven aan de voorkant van je website.  
In het wp-admin gedeelte heb je alvast een paar items toegevoegd, deze kunnen wij nu gaan weergeven.  
Dit gaan wij op verschillende manieren doen:  
1. via het menu
2. via een widget
3. via de categorie
4. de pagina zelf

---
### 1- De post type toevoegen aan het menu 
![menu.png](images%2Fmenu.png)
Dit is eigenlijk de makkelijkste omdat je hier geen code voor hoeft te schrijven.
1. ga in het admin menu naar het **menu** onderdeel toe.
2. selecteer aan de zijkant je custom **post type**
3. klik op `view all` en selecteer je post type
4. klik op 'Add to Menu'
5. Sla het menu op
6. Bekijk nu je website in je browser en zie dat je een nieuw menu item hebt.

---
### 2- De post type toevoegen aan een widget
![widgets.png](images%2Fwidgets.png)
In het wp-admin gedeelte kun je via de `customizer` of direct naar het `widgets` menu gaan.  
Hier kun je een tekst plaatsen met een link naar de slug van jouw `custom post type`, bij mij is dat `\wood`.
Gebruik hiervoor de link knop, of schrijf dit zelf in HTML.

---
### 3- Weergave van de categorie
![wood.png](images%2Fwood.png)
Jouw custom post type is te bereiken door de slug als endpoint in de browser toe te voegen, in mijn geval: [localhost/wood](http:localhost/wood)  
Om een mooi overzicht te krijgen maak ik hier ook een speciale archief pagina van door de index te **dupliceren** naar `archive-wood.php`  
_( bij jou is dat natuurlijk niet wood, maar jouw eigen post type )_  
In dit overzicht heb ik bijvoorbeeld de thumbnails weergegeven en een titel toegevoegd.  

Op dezelfde manier kunnen wij ook de categorie weergeven, nu alleen met de categorie in de titel.  
Ik kopieer nu de `archive-wood.php` naar `taxonomy-origin.php`  
Het enige dat ik voorlopig aanpas is de titel, daarvan maak ik:  
```php
<h1>
    Dit is mijn categorie: <?php single_term_title() ?>
</h1>
```

---
### 4- Controleer
Als je nu naar jouw website gaat in de browser dan zie je dat je op verschillende manieren naar jouw custom post type kan gaan.  
Ook zie je dat je overzicht pagina's hebt en verschillende enkele pagina's.  
Het klopt dat er nu hier en daar duplicated code is, maar daar gaan wij een volgende stap mee aan de slag.  


---
{% include commit_push.md %}

