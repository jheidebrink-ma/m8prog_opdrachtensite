---
title: Les 7
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Registreren van een custom post type
{: .text-green-100 .fs-6 }

In deze les ga je een custom post type registreren.  
Ik gebruik `wood` als voorbeeld, jij moet voor jezelf een ander type gaan gebruiken.  

---
### 1- Structuur
Om mijn project gestructureerd te houden heb ik eerst een folder aangemaakt in CammelCase met de naam van het thema.  
In mijn geval `M8progCustom`  
Hierin plaats ik de functionaliteiten, om te beginnen met post-types, daarom heb ik daarom het volgende php document aangemaakt:  
`PostType.php`
Dit bestand moet je natuurlijk wel laden, dat doe je door deze via de php `require_once` te implementeren in de `functions.php`.

---
### 2- Labels
Voordat wij gaan registreren definiëer ik de labels van dit post-type zodat straks dit element goed terug kan vinden.
Dit doe ik door in mijn `PostType.php` document de volgende code te plaatsen.  
{: .mb-0 }
## Let op dat je de juiste **term** en **text-domein** gebruikt!  
{: .text-red-100 .fs-4 .mt-2 .mb-4 }

```php
$labels = [
	'name'               => __( 'Woods', 'Text_Domain' ),
	'singular_name'      => __( 'Wood', 'Text_Domain' ),
	'add_new'            => __( 'New Wood', 'Text_Domain' ),
	'add_new_item'       => __( 'Add New Wood', 'Text_Domain' ),
	'edit_item'          => __( 'Edit Wood', 'Text_Domain' ),
	'new_item'           => __( 'New Wood', 'Text_Domain' ),
	'view_item'          => __( 'View Wood', 'Text_Domain' ),
	'search_items'       => __( 'Search Wood', 'Text_Domain' ),
	'not_found'          => __( 'No Wood Found', 'Text_Domain' ),
	'not_found_in_trash' => __( 'No Wood found in Trash', 'Text_Domain' ),
];
```

---
### 3- Definiëren van de argumenten voor je custom post type
De volgende stap is het definiëren van de argumenten.  
Eén van de argumenten is de array met labels die we al toegevoegd hebben.
Onder de labels, en nog steeds binnen de haken, voeg je dit toe:
```php
$args = [
	'labels'       => $labels,
	'has_archive'  => true,
	'public'       => true,
	'hierarchical' => false,
	'supports'     => [
		'title',
		'editor',
		'excerpt',
		'custom-fields',
		'thumbnail',
		'page-attributes',
	],
	'rewrite'      => [ 'slug' => 'wood' ],
	'show_in_rest' => true,
];
```
Laten we eens kijken wat deze allemaal doen:
- **Labels:** de array met labels die we al eerder definieerden.
- **has_archive:** zorgt dat je een post type archief voor je custom post type kunt maken. 
- **public:** zorgt dat het post type ook verschijnt binnen de zoekresultaten. Dit staat standaard uit en wil ik graag inschakelen.
- **hierarchical** waarde hangt af van hoe je precies je custom post type wilt gaan gebruiken. Als je dit op `true` zet, zal het post type zich gedragen als het pagina-type, waarbij je een hiërarchie kunt aanbrengen met parent en child-berichten. Als je dit op `false` zet, zal het zich gedragen als een gewoon bericht, zonder hiërarchie.
- **supports** array definieert een aantal features van post types die dit custom type kan ondersteunen. Verschillende opties zijn: 'title', 'editor', 'comments', 'revisions', 'trackbacks', 'author', 'excerpt', 'page-attributes', 'thumbnail', 'custom-fields', en 'post-formats'.
- **rewrite** kun je gebruiken om je taxonomie een andere te geven.
- **show_in_rest** zorgt ervoor dat het post type toegankelijk is via de REST API en de admin interface.
Hier vind je de complete uitleg: [https://developer.wordpress.org/reference/functions/register_post_type/](https://developer.wordpress.org/reference/functions/register_post_type/)

---
### 4- Registratie
Het registreren is nadat je alles hebt ingesteld super simpel, je hoeft alleen de post-type en de argumenten door te geven.  
```php
register_post_type( 'wood', $args );
```

---
### 3- Controleer
Ga nu naar je admin omgeving en zie dat in het menu een nieuw item is toegevoegd.  
### Voeg nu **minimaal 2 custom post types** toe aan je website.
{: .text-red-100 .fs-4 }

---
### Links
[https://developer.wordpress.org/reference/functions/register_post_type/](https://developer.wordpress.org/reference/functions/register_post_type/)
[https://developer.wordpress.org/reference/functions/register_taxonomy/](https://developer.wordpress.org/reference/functions/register_taxonomy/)

---
{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
In de volgende opdracht ga je een `categorie` toevoegen.  
[Registreren van een taxonomie](taxonomy)


