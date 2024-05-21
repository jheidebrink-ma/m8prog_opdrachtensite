---
title: Les 7
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Registreren van een custom post type
{: .text-green-100 .fs-6 }

Nu ga je een taxonomy registreren zodat je custom post type onderverdeeld kan worden in categorieën.

---
### 1- Labels
Voordat wij gaan registreren definiëer ik de labels van deze taxonomy.
Dit doe ik door in mijn `PostType.php` document de volgende code te plaatsen.
{: .mb-0 }
## Let op dat je de juiste **term** en **text-domein** gebruikt!  
{: .text-red-100 .fs-4 .mt-2 .mb-4 }
```php
$labels = [
	'name'              => _x( 'Origins', 'taxonomy general name', 'Text_Domain' ),
	'singular_name'     => _x( 'Origin', 'taxonomy singular name', 'Text_Domain' ),
	'search_items'      => __( 'Search Origins', 'Text_Domain' ),
	'popular_items'     => __( 'Popular Origins', 'Text_Domain' ),
	'all_items'         => __( 'All Origins', 'Text_Domain' ),
	'parent_item'       => __( 'Parent Origin', 'Text_Domain' ),
	'parent_item_colon' => __( 'Parent Origin:', 'Text_Domain' ),
	'edit_item'         => __( 'Edit Origin', 'Text_Domain' ),
	'update_item'       => __( 'Update Origin', 'Text_Domain' ),
	'add_new_item'      => __( 'Add New Origin', 'Text_Domain' ),
	'new_item_name'     => __( 'New Origin Name', 'Text_Domain' ),
	'menu_name'         => __( 'Origins', 'Text_Domain' ),
];
```

---
### 2- Definiëren van de argumenten voor je taxonomy
De volgende stap is het definiëren van de argumenten.  
Eén van de argumenten is de array met labels die we al toegevoegd hebben.
Onder de labels, en nog steeds binnen de haken, voeg je dit toe:
```php
$args = [
	'hierarchical'      => true,
	'labels'            => $labels,
	'show_ui'           => true,
	'show_admin_column' => true,
	'query_var'         => true,
	'show_in_rest'      => true,
	'rewrite'           => [ 'slug' => 'origin' ],
];
```
Laten we eens kijken wat deze allemaal doen:
- **hierarchical** waarde hangt af van hoe je precies je custom post type wilt gaan gebruiken. Als je dit op `true` zet, zal het post type zich gedragen als het pagina-type, waarbij je een hiërarchie kunt aanbrengen met parent en child-berichten. Als je dit op `false` zet, zal het zich gedragen als een gewoon bericht, zonder hiërarchie.
- **labels:** de array met labels die we al eerder definieerden.
- **show_ui** is dit onderdeel wel of niet zichtbaar in de admin omgeving 
- **show_admin_column** in het admin overzicht van mijn custom post types kan er een kolom bij komen met deze taxonomy
- **query_var** mag dit element wel of niet opgehaald worden via de wp-query
- **show_in_rest** zorgt ervoor dat het post type toegankelijk is via de REST API en de admin interface.
- **rewrite** wil je dat de slug voor deze taxonomy niet gelijk is aan de naam?
Hier vind je de complete uitleg: [https://developer.wordpress.org/reference/functions/register_taxonomy/](https://developer.wordpress.org/reference/functions/register_taxonomy/)

---
### 3- Registratie
Het registreren is nadat je alles hebt ingesteld super simpel, je hoeft alleen de post-type en de argumenten door te geven.  
```php
register_taxonomy( 'origin', 'wood', $args );
```

---
### 3- Controleer
Ga nu naar je admin omgeving en zie dat in het menu een nieuw item is toegevoegd.  
En dat je bij het bewerken van een custom post type item een categorie kunt selecteren of aanmaken.  
### Voeg nu **minimaal 2 taxonomies** toe en koppel deze aan een of meerdere custom post types.  
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
In de volgende opdracht ga je deze `taxonomy` én `post type` weergeven op jouw site.  
[Weergeven van een Custom post type](view)


