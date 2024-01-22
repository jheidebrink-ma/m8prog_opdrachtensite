---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Database migration maken voor file upload
{: .text-green-100 .fs-6 }

Je moet eerst een veld toevoegen om straks de bestandsnaam in op te slaan.  Dat doe je door een nieuwe database wijziging (migration) te maken en het veld toe te voegen.  
Daarna gebruik je `php artisan migrate` om de wijziging door te voeren in de database.

---
### 2- De database
Wij gaan straks bestanden opslaan op de folder, maar die willen wij ook weer kunnen uitlezen aan de voorkant de website doordat deze gekoppeld is met een project.  
Het is namelijk belangrijk dat je weet welke foto je op welk moment moet weergeven.  
Een nieuwe migratie maak je via `php artisan` of als je met sail werkt, via `sail artisan`.
Gebruik daarvoor het volgende commando:
```shell
[php of sail] artisan make:migration migratie_naam
```
Bijvoorbeeld:
```shell
php artisan make:migration create_image_table
```
Vervolgens open je deze migratie die je tegenkomt in de database/migrations folder.  
Met deze migratie gaan wij de products folder aanpassen zodat er een image kolom bij komt.

Open deze migratie en vog de volgende velden toe:
- ti


---

### Optionele video:

{% include youtube.md video="6vnKESFnyk0" %}

---

{% include commit_push.md %}


