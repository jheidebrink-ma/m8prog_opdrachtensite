---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## File upload veld toevoegen
{: .text-green-100 .fs-6 }

Je gaat een file upload veld toevoegen en het formulier aanpassen zodat het bestand ook goed wordt meegestuurd.

---
### 1- multipart/form-data
Om bestanden via een html formulier te versturen moet je eerst in het formulier aangeven dat er verschillende type data verstuurd kan worden.  
Wij zijn nu bezig in dit formulier:
```html
/resources/views/dashboard/projects/form.blade.php
```
Voeg de `enctype` attribute toe aan je form tag:
```html
 enctype="multipart/form-data"
```

---
### 2- Image field
Nu kun je een image veld toevoegen aan je formulier.  
Dat kan bijvoorbeeld zo'n veld zijn:

```html
    <input type="file" name="plaatje">
```

---
### 3- Image verwerken in de controller
Als het formulier verstuurd is dan moet ook dit veld verwerkt worden.  
Open daarom de controller die de het formulier verwerkt.  
```app/Http/Controllers/ProjectAdminController.php```
Op twee plakken verwerk je het formulier: `store` en `update`.  
Wij beginnen met het aanpassen van de `store`, dan kunnen wij daarna de code kopiëren naar de andere functie.
Onthoud hoe je de `name` van het veld hebt ingesteld, bij mij is dat `plaatje` waardoor ik nu het bestand via de request zo opvangen:
```php
    $image = $request->file('plaatje');
    dd($image);
```
Als je het formulier nu verstuurd dan zie je diverse informatie en kun je aan de slag met het opslaan van de afbeelding.


---
### Optionele video:
{% include youtube.md video="AaJLsFd2mfc" %}

### Links
- [Storage in Laravel](https://laravel.com/docs/10.x/filesystem)

Zorg dat je file upload veld werkt en dat je het bestand kunt opvragen in je controller met de `dd()` functie.
{: .text-blue-100 .fs-4 }

---
{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[File upload valideren en bewaren in storage](file-storage)
