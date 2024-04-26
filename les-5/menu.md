---
title: Les 5
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Het WordPress menu
{: .text-green-100 .fs-6 }

Binnen WordPress heb je een uitgebreid menu systeem, dat gaan wij nu implementeren in oze template.  
Zo kan de beheerder zelf het menu beheren.

---
## 1- Menu ondersteuning toevoegen
In de `functions.php` moet je even aangeven jouw thema menu functionaliteit ondersteunt. 
Dit doe je door in te haken op de `init` action van WordPress, in een latere les gaan wij verder in op _actions_ en _hooks_. 
```php
function register_my_menus() {
	register_nav_menus(
		[
			'header' => __( 'Header Menu', 'Text_Domain' ),
			'other'  => __( 'Other Menu', 'Text_Domain' ),
		]
	);
}

add_action( 'init', 'register_my_menus' );
```

## 2- Extra filters
Omdat ik in mijn voorbeeld gebruik maak van Bootstrap moet ik een extra aanpassing doen om het menu te laten voldoen aan het Bootstrap formaat.  
Daarom voeg ik ook deze filters toe aan functions.php  
```php

/**
 * Function to add extra classes to the menu list element
 * @usage:
 *      Add 'add_li_class'  => 'nav-item',
 *      as an extra option to wp_nav_menu()
 *
 * @param $classes
 * @param $item
 * @param $args
 *
 * @return mixed
 */
function add_additional_class_on_li($classes, $item, $args) {
	if(isset($args->add_li_class)) {
		$classes[] = $args->add_li_class;
	}
	return $classes;
}
add_filter('nav_menu_css_class', 'add_additional_class_on_li', 1, 3);

/**
 * Function to add extra classes to the menu anchor element
 * @usage:
 * Add 'add_li_class'  => 'nav-item',
 * as an extra option to wp_nav_menu()
 *
 * @param $attributes
 * @param $item
 * @param $args
 *
 * @return mixed
 * /
 */
function add_additional_class_on_a($attributes, $item, $args) {
	if(isset($args->add_a_class)) {
		$attributes['class'] .= ' ' . $args->add_a_class;
	}
	return $attributes;
}
add_filter('nav_menu_link_attributes', 'add_additional_class_on_a', 1, 3);

```

---
## 3- Aanmaken van een menu
In het `wp-admin` gedeelte kun je onder 'Appearance' en dan het kopje `menus` een nieuw menu aanmaken.  
Geef ook aan op welke `Display location` deze moet verschijnen. 
![menu.png](images%2Fmenu.png)

---
## 4- Menu weergeven in de header
Nu je een menu hebt aangemaakt wil je hem natuurlijk ook weergeven aan de voorkant van je website.  
In de header heb je al een statisch menu, nu gaan wij het statische code vervangen door een dynamische.  
Bekijk hier de configuratie opties: [https://developer.wordpress.org/reference/functions/wp_nav_menu/](https://developer.wordpress.org/reference/functions/wp_nav_menu/)  
_Ik heb twee extra opties toegevoegd die ik kan gebruiken door de filters die hierboven staan._  
Dit is de code om een `header` menu op te halen in de bootstrap stijl.  
```php
<?php
    wp_nav_menu(
        [
            'menu'            => 'header',
            'link_before'     => '',
            'link_after'      => '',
            'menu_class'      => 'navbar-nav me-auto mb-2 mb-lg-0',
            'container'       => 'div',
            'container_class' => 'collapse navbar-collapse',
            'container_id'    => 'navbarSupportedContent',
            'add_li_class'    => 'nav-item',
            'add_a_class'     => 'nav-link',
        ]
    );
?>
```

---
## 5- Controleer
Bekijk je website nu in de browser en zie dat je een mooi menu hebt.

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Widgets implementeren](widgets)
