---
title: Les 3
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Routes, controllers en view maken
{: .text-green-100 .fs-6 }

Wij gaan nu een aantal routes maken voor je website. In eerste instantie wil ik deze pagina maken: http://localhost/about

**Schrijf per pagina/functionaliteit op:**

- De titel van de pagina
- Een mooie url, bijvoorbeeld: `/projecten` of `/about` of `/contactformulier`.
- De naam van de controller, bijvoorbeeld `ProjectController`, `AboutController`, `ContactController`.

---

## Maak routes, controllers en views voor jouw website

Voor alle pagina's ga je nu een route maken, een controller en een view.
Daarna ga je de pagina's in je navigatie zetten zodat je door de site kan klikken (met nog lege pagina's)

### PHP Artisan
Je kunt routes met de hand maken door verschillende documenten aan te maken. Maar Laravel kan je ook via de Artisan console commando's uitvoeren. Zie voor meer informatie:
[https://laravel.com/docs/10.x/artisan](https://laravel.com/docs/10.x/artisan)

### Controller aanmaken
Om een controller aan te maken gebruik je dit commando:
`php artisan make:controller controllerName`

Bijvoorbeeld voor mijn about pagina wat wij nu gaan aanmaken:
`php artisan make:controller AboutController`
_let op dat je deze naam CammelCase is en met een kapitaal begint_

Later gaan wij models aanmaken en migraties, om een model aan te maken gebruik je dit commando:
`php artisan make:model modelName`

Om meerdere elementen te gelijk aan te maken kun je bijvoorbeeld het volgende commando uitvoeren om een model én een controller aan te maken:
`php artisan make:model modelName -c`

Je kunt ook een combinatie maken, hierbij een aantal opties:
- `-c`, `--controller` Create a new controller for the model
- `-f`, `--factory` Create a new factory for the model
- `--force` Create the class even if the model already exists
- `-m`, `--migration` Create a new migration file for the model
- `-s`, `--seed` Create a new seeder file for the model
- `-p`, `--pivot` Indicates if the generated model should be a custom intermediate table model
- `-r`, `--resource` Indicates if the generated controller should be a resource controller

## Controller configureren
In de /app/Http/Controllers vind je nu de nieuwe Controller, `AboutController` open deze.
Voeg de volgende publieke functie toe:
```
public function index() {
    return 'Dit is de about pagina.';
}
```
Nu heb je een functie gemaakt die wij als route kunnen aanroepen.

## Routes
Ga nu naar het bestand: `/routes/app.php`
Daar kun je een route aanmaken die naar deze functie verwijst. Geef hierbij aan:
- Welke request methode je gebruikt: `GET` / `POST` / `DELETE` / `PATCH` / `PUT`
- Wat de url is
- Welke class je aanroept
- Welke functie je binnen die class aanroept
Bijvoorbeeld:
```
Route::METHOD(URL, CLASS)->name(INTERNE_NAAM);
```
Bijvoorbeeld voor onze about pagina:
```
Route::get('/about', [ \App\Http\Controllers\AboutController::class, 'index'])->name('about');
```

### Controle
Bekijk nu wat er in de browser gebeurd door naar de about pagina te gaan, bijvoorbeeld:
http://localhost:89/about

## Video
Kijk de video om te zien hoe je dat doet:
{%include youtube.md video="YdAnPq6hMZo" %}

---

Zorg dat je na deze video alle routes hebt voor jouw website waarmee je jouw user stories kunt gaan uitwerken.
{: .text-blue-100 .fs-4 }

---

### Meer uitleg en ondersteuning?

In de Laravel documentatie staat ALLE uitleg over hoe je routes en controllers gebruikt, met voorbeelden.

- [Laravel Routes](https://laravel.com/docs/routing)
- [Laravel Controllers](https://laravel.com/docs/controllers)

---

{% include commit_push.md %}


