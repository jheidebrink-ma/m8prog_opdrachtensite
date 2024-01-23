---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## File weergeven
{: .text-green-100 .fs-6 }

Je gaat een het bestand weergeven bij projecten.

---
### 1- Link de storage folder
De storage folder is niet direct zichtbaar in je public folder. Daarom moet je een symlink maken om deze zichtbaar te maken in de public folder.
Hiervoor kun je het volgende commando gebruiken:
```shell
[php of sail] php artisan storage:link
```
Bijvoorbeeld:
```shell
php artisan php artisan storage:link
```
Nu is de public folder die in de storage/app folder staat ook te benaderen door de browser. 

---
### 2- Voeg de image toe aan de view
Ga naar de view van een project toe. 
Open bijvoorbeeld: `resources/views/projects/show.blade.php`
Voeg daar ergens de controle toe of een project wel een image heeft:
En geef binnen die if de afbeelding weer:
```php
@if($project->image)
    <img src="{{Storage::url($project->image)}}">
@endif
```




---

### Geen optionele video.
Er is geen video voor deze les.

Zorg dat je file upload veld werkt en dat je het bestand kunt opvragen in je controller met de `dd()` functie.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


