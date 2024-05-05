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
### 2- Thema beschikbaar maken voor een vertaling
Dit kun je met de hand doen, of gebruik maken van WP CLI.  
Ik kies voor WP CLI omdat dan diverse onderdelen direct ingesteld worden.  
Voer dit commando uit:  
```shell
  wp i18n make-pot path/to/your-plugin-directory
```
## Let op, je moet wel de correcte folder opgeven.



---
### Links
[https://developer.wordpress.org/apis/internationalization/localization/](https://developer.wordpress.org/apis/internationalization/localization/)

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Aanpassen van gegevens met een formulier](form-edit)
