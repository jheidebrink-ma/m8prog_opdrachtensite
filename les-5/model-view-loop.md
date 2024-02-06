---
title: Les 4 
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Gegevens ophalen in controller en weergeven in de view
{: .text-green-100 .fs-6 }

Je kunt nu (na wat oefenen) alle CRUD operaties uitvoeren met de Eloquent model class.

Nu kun je een lijst pagina gaan maken door gegevens op te halen en aan een view te geven.

In de view kun je met de Blade `@foreach` directive de gegevens tonen met jouw eigen HTML en CSS.

---
### 1- Maak een functie aan in je ProjectController
Zoek via het `php artisan route:list` op wat de naam van de route voor het aanmaken van een project.
Kopieer die naam en maak in de `dashboard/projects/index.blade.php` een link naar deze route.
```php
{% raw %}
<a href="{{route('ROUTE-NAAR-CREATE')}}" class="bg-green hover:bg-green text-white font-bold py-2 px-4 rounded float-right">
    {{ __('New project') }}
</a>
{% endraw %}
```

---
### 2- Haal alle projecten op

---
### 3- Maak een view bestand 

---
### 4- Maak een route aan

---
### 5- Test de route


---

### Optionele video:
In de video laat ik zien hoe je dit doet.  
{% include youtube.md video="tsZTDguVaBs" %}

---

Zorg dat je na deze opdracht een werkende lijst pagina hebt met gegevens uit de database. In de volgende les ga je een formulier maken om gegevens via de model class op te slaan.
{: .text-blue-100 .fs-4 }

Ook leer je hoe je forms veilig maakt met CSRF en hoe je gegevens makkelijk kunt valideren met Laravel. Ook ga je gebruiksvriendelijke foutmeldingen als de ingevulde gegevens niet geldig zijn.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


