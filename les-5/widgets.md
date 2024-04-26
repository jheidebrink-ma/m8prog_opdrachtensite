---
title: Les 5
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Wat zijn WordPress-widgets?
{: .text-green-100 .fs-6 }

In WordPress kun je stukjes content maken die je buiten de artikelen en bijbehorende inhoud beheert, dit noemen wij widgets.  
Widgets kunnen diverse type informatie bevatten zoals HTML, navigatiegegevens of andere data die niet direct verbonden is aan de huidige pagina.  
In de meeste gevallen wordt een widget op elke pagina van je site weergegeven, maar je kan ook widget gebieden toevoegen voor specifieke pagina's, zoals je homepagina.
Om een widget aan je site toe te voegen, moet je deze toevoegen aan een widget-gebied. 

---
## 1- Widget ondersteuning toevoegen aan thema
Widget-gebieden kun je definiëren in het thema als je hier gebruik van wilt maken.
In de `functions.php` ga ik aangeven dat mijn thema een widget gebied heeft zodat ik deze in het wp-admin gedeelte kan beheren.
Dit doe je door in te haken op de `widgets_init` action van WordPress. 
```php
/**
 * Initialize the widget area
 * 
 * @return void
 */
function add_theme_widgets() {
	register_sidebar( [
		                  'name'          => __( 'Footer Widget Area', 'Text_Domain' ),
		                  'id'            => 'footer-widget-area',
		                  'description'   => __( 'A widget area located in the footer.', 'Text_Domain' ),
		                  'before_widget' => '<div id="%1$s" class="widget-container %2$s">',
		                  'after_widget'  => '</div>',
		                  'before_title'  => '<h3 class="widget-title">',
		                  'after_title'   => '</h3>',
	                  ] );
}

add_action( 'widgets_init', 'add_theme_widgets' );
```

---
## 2- Instellen van een widget
In het `wp-admin` gedeelte kun je onder 'Appearance' en dan het kopje `widgets` je widgets beheren.  
![widgets.png](images%2Fwidgets.png)

---
## 3- Widget weergeven in de footer
Nu je een widget hebt ingesteld wil je hem natuurlijk ook weergeven aan de voorkant van je website.  
In het `<footer>` element wil ik graag een widget weergeven.  
Bekijk hier de configuratie opties: [https://developer.wordpress.org/reference/functions/register_sidebar/](https://developer.wordpress.org/reference/functions/register_sidebar/)  
Dit is de code om een widget weer te geven, waarbij de ID gelijk is aan `footer-widget-area`.  
```php
<?php if ( is_active_sidebar( 'footer-widget-area-3' ) ) : ?>
    <?php dynamic_sidebar( 'footer-widget-area-3' ); ?>
<?php endif; ?>
```
Je kunt natuurlijk ook meerdere gebieden aanmaken waarin je widgets verschijnen.  
Zo kun je eenvoudig de footer van je project beheren vanuit de wp-admin omgeving.

---
## 4- Controleer
Bekijk je website nu in de browser en zie dat je extra data in de content hebt.

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
In de volgende opdracht ga je zelf een `loop` maken.  
[WordPress Loop uin de index](index_loop)
