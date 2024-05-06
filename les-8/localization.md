---
title: Les 8
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Wat is lokalisatie binnen WordPress?
{: .text-green-100 .fs-6 }

Een WordPress thema of plugin kan een eigen vertaling hebben voor verschillende onderdelen zoals buttons, labels en andere vaste onderdelen.  
Binnen WordPress kun je redelijk eenvoudig een thema of plugin vertalen, dit noemen wij Lokalisatie.  
Lokalisatie wordt afgekort als **l10n** _(omdat er 10 letters tussen de l en de n staan)_.

---
### 1- Text-domein instellen
In de `style.css` kun je het **text-domein** instellen.  
Dit is een `string` waarin je de naam van het thema aangeeft.  
Binnen je thema gebruik je deze string al op verschillende plekken.  
Dat doe je met deze regel: 
```
    Text Domain:       m8prog-custom
```
Die waarde gebruik je overal waar je een vertaalde tekst wilt terug geven _( `return` )_.  
Dit heb je al een paar keer gedaan, bijvoorbeeld hier:  
``` 
    __( 'Header Menu', 'm8prog-custom' )
```
Of als je direct iets wilt weergeven _( `echo` )_
``` 
    _e( 'Header Menu', 'm8prog-custom' )
```

---
### 2- Thema vertalen
![poedit.jpg](images%2Fpoedit.jpg)  
Er zijn verschillende tools om een thema of plugin te vertalen.  
In mijn voorbeeld maak ik gebruik van [Poeedit](https://poedit.net/download)  
Deze tool kan alle bestanden van je thema of plugin laten controleren en zie precies wat je moet vertalen.  
Nadat je het **\*.pot** bestand vertaald hebt en opgeslagen heb je een **\*.po** én een **\*.mo** bestand.  
Deze bestanden bevatten jouw echte vertalingen.  
Maak nu een nederlandse vertaling van je project _(nl_NL)_.  

---
### 3- Locatie van de vertalingen instellen
WordPress weet niet standaard waar de vertalingen staan, daarom moeten wij een via een `action-hook` aangeven waar de bestanden staan.  
Door een nieuwe actie toe te voegen aan de `after_setup_theme` hook zullen de vertalingen geladen worden nadat WordPress het thema heeft geïnitialiseerd.  
Dat doe je door deze code toe te voegen aan je `functions.php`:  
```php

/**
 * Tell WordPress where the localization files are
 * 
 * @return void
 */
function load_custom_textdomain()
{
	load_theme_textdomain( 'm8prog-custom', get_template_directory() . '/languages' );
}
add_action('after_setup_theme', 'load_custom_textdomain');
```

---
### 4- Vertaling controleren
In [wp-admin](http://localhost/wp-admin/profile.php) kun je naar jouw profiel gaan door rechtsboven op je naam te klikken.  
Halverwege deze pagina kun je een taal selecteren, selecteer hier nu `Nederlands` en sla de wijzigingen op.  
Als je nu in de `wp-admin` omgeving naar het `Widgets` onderdeel gaat dan zie je nu dat de onderdelen in het Nederlands zijn.
![translated.png](images%2Ftranslated.png)


---
### Links
- [developer.wordpress.org localization](https://developer.wordpress.org/apis/internationalization/localization/)
- [Poeedit](https://poedit.net/download)

---

{% include commit_push.md %}
