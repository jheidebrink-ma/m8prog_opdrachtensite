---
title: Les 8
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Form validatie en foutmeldingen
{: .text-green-100 .fs-6 }

Nu wordt het tijd om de ingevulde gegevens te valideren, zodat er geen lege artikelen in de database kunnen komen (in mijn geval)
Je doet dit door validatie regels per invoerveld te bedenken en je gebruikt de `validate()` method van de `$request` om de validatie uit te voeren.

Is een veld niet goed ingevuld dan stuurt Laravel je automatisch terug naar het formulier, zodat je de foutmelding(en) kunt tonen. Ook kun je de oude invoer weer in het veld zetten zodat je het niet opnieuw hoeft in te vullen.

### Meer informatie
Ga naar de Laravel website en bekijk welke validatie regels er beschikbaar zijn: [Alle validatie regels](https://laravel.com/docs/10.x/validation#available-validation-rules)


---
### 1- Request data controleren
We gaan nu verstuurde informatie weergeven.   
Open de controller waar je de CRUD functionaliteit in hebt staan, waarschijnlijk is dat `ProjectAdminController`.. 
Wij gaan nu werken in de `store` functie.  
Als argument zie je dat er een Request object meegegeven moet worden: 
```php
 public function store(Request $request)
 ```
Dit object kun je weergeven door gebruik te maken van de **debug dump()** `dump()` of **debug die()** `dd()` functie van Laravel.
Probeer dit maar eens uit:
```php
    public function store(Request $request)
    {
        dump( $request->all() );
    }
 ```
---
Je ziet nu alle velden die verstuurd zijn vanuit het formulier.  
Probeer nu één veld weer te geven, bijvoorbeeld zo:
```php
    public function store(Request $request)
    {
        $valid = $request->validate([
            'title' => 'required|unique:posts|max:255',
            'body' => 'required',
        ]);
    }
 ```

---
### 2- Validatie instellen
Je weet nu hoe je de data kunt ophalen, nu gaan wij aan de slag met de validatie.  
Dit kan op twee manieren, of je plaatst het resultaat in een variabele óf je stopt het script als het niet goed is.  
De eerste optie is voor straks makkelijker omdat we dan gelijk de valide data hebben.  
Je moet per element aangeven of het verplicht is en of je verschillende eisen hebt. 
Als de titel bijvoorbeeld verplicht is, uniek moet zijn in de posts tabel én hij maximaal 255 karakters mag bevatten dan zou dit werken.   
```php
    public function store(Request $request)
    {
        $valid_data = $request->validate([
            'title'      => 'required|unique:posts|max:255',
            'onderdeel'  => 'required',
        ]);
        
        dd($valid);
    }
 ```
Nu weet je alleen nog niet of het goed is gegaan, daarom moet je in de view bij het formulier ook de error weergeven als die er is.  
Dat doe je door deze code op de plek te plaatsen waar je de errors wilt zien, bijvoorbeeld in views/dashboard/create.blade.php:
```php
{% raw %}
@if ($errors->any())
    <div class="p-2 bg-yellow border-2 rounded">
        <ul>
            @foreach ($errors->all() as $error)
                <li>{{ $error }}</li>
            @endforeach
        </ul>
    </div>
@endif
{% endraw %}
```
1. Hierbij controleer ik eerst of er errors zijn.
2. Als dat het geval is dan laat ik een list zien.
3. In deze list plaats ik alle errors met een foreach loop.


---
### 3- Weergeven van oude data
Het is prettig als je een formulier invult je nog wel de oude data ziet, hiervoor moet je de oude values toevoegen aan de invul velden.  
Dit doe je door een value toe te voegen, in dit geval voor het veld titel:
```html
{% raw %}
<input name="title" type="text" value="{{old('title')}}" />
{% endraw %}
```

---

### Optionele video:

{% include youtube.md video="az8ZV_XQJmI" %}

Zorg dat je een formulier hebt met validatie regels en foutmeldingen en dat de "oude" inpout were wordt getoond als er validatie errors zijn, zodat je niet alles opnieuw hoft in te vullen.
{: .text-blue-100 .fs-4 }

### Links
- [Documentatie over requests](https://laravel.com/docs/10.x/requests)
- [Documentatie over form validatie](https://laravel.com/docs/10.x/validation)
- [Alle validatie regels](https://laravel.com/docs/10.x/validation#available-validation-rules)
- [Documentatie over foutmeldingen tonen ](https://laravel.com/docs/10.x/validation#quick-displaying-the-validation-errors)
- [Documentatie over tonen van eerdere invoer](https://laravel.com/docs/10.x/requests#old-input)

---

{% include commit_push.md %}


