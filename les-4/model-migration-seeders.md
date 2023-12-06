---
title: Les 4 
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Een seeder maken
{: .text-green-100 .fs-6 }

Op dit moment heb je een tabel gemaakt met bijbehorend model. Nu is het tijd om ook wat voorbeeld data in de tabel te plaatsen.
Dat doe je door gebruik te maken van Seeders.

## Seeder aanmaken
Eerst gaan we een nieuw zaadje planten in de database:
```shell
php artisan make:seeder ProjectSeeder
```

Er is nu een nieuwe seeder aangemaakt waarmee een project toegevoegd kan worden.
Open maar het bestand: 
/database/seeders/ProjectSeeder.php

Hier vind je de `run` functie. Deze voert het toevoegen uit.
Je kunt nu een database query maken, Laravel Eloquent gebruiken om je data teo te voegen. 
Dit laatste is het eenvoudigst en lijkt het meeste op zoals wij straks met models omgaan.
Het is ook mogelijk om gebruik te maken van **Model Factories** hierbij kun je een aantal items met random data zoals fake tekst toevoegen.
Plaats voor één project de volgende code, let op dat je deze overschrijft zodat je namespacing automatisch ingesteld word.:

**Elementen**
Vul de verschillende elementen van het model.<br>
Velden die jij zelf hebt bedacht maar hier niet staan zul je moeten toevoegen.
```shell
        DB::table('projects')->insert([
            'titel'         => 'Mijn project titel',
            'description'   => 'Enim labore eu, sed. Sed esse incididunt aute velit. Incididunt, aute velit duis amet sint. Duis amet sint pariatur esse anim officia mollit. Sint pariatur esse anim. Esse anim officia mollit laboris aliqua, et esse.',
            'active'        => true,
        ]);
```

## Migratie uitvoeren
Voor het toevoegen van de tabel en instellingen hoeven wij geen mysql te schrijven, maar kan ik Laravel de opdracht geven om dit uit te voeren. 
Gebruik hiervoor de migratie functionaliteit van Laravel:
```shell
// Wanneer je gebruik maakt van de originele docker setup
php artisan db:seed --class=ProjectSeeder
```
```shell
// wanneer je gebruik maakt van sail
sail artisan db:seed --class=ProjectSeeder
```

De kans is groot dat je nu een error ziet doordat Artisan geen verbinding kan maken met de database. De oplossing hiervoor is door dit commando uit te voeren vanaf de laravel / php instance in Docker.
Open daarvoor het terminal venster door in docker desktop op de drie puntjes achter de betreffende container te klikken.

Open nu de database interface ( via een app of phpmyadmin ) en controleer of de data is toegevoegd. 

---
Meer informatie kun je vinden in deze video:
{% include youtube.md video="WGYmEdzZgtM" %}

---

{% include commit_push.md %}


