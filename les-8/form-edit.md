---
title: Les 8
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Aanpassen gegevens met een formulier
{: .text-green-100 .fs-6 }

Het is natuurlijk leuk om gegevens toe te voegen, maar af en toe wil je ook iets kunnen wijzigen.
Daarom ga je het formulier herbruiken om een rij uit de database table aan te passen.

---
### 1- Toevoegen van een wijzig link
Plaats bij elk project in het dashboard overzicht een `wijzig` link. De link naar deze actie is de route `model.edit`, waarbij je het model als referentie moet meegeven.  
Bijvoorbeeld: ``` route('project.edit', $project) ```.  
Deze url kun je opvragen door het volgende php artisan commando uit te voeren in de terminal: 
```shell
 php artisan route:links
 ```  
**Note:** Zorg ervoor dat deze knop alleen zichtbaar is voor mensen die ingelogd zijn.  
Voorbeeld, in mijn geval is dit een link die eruit ziet als een knop.
```php
{% raw %}
<a href="{{route('project.edit', $project)}}"
class="bg-yellow me-2 focus:outline-none text-white bg-purple-700 hover:bg-purple-800 focus:ring-4 focus:ring-purple-300 font-medium rounded-lg text-sm px-5 py-2.5 mb-2 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-900">
Wijzig
</a> 
{% endraw %}
```

---
### 2- Het formulier voorbereiden
Om het project aan te kunnen passen hebben wij een view nodig met een formulier.  
Hiervoor wil ik het formulier van de create gebruiken, maar ik wil hem niet kopiëren zodat ik het maar één keer hoef te onderhouden.  
Knip daarom het formulier uit het create formulier _( ```resources/views/dashboard/projects/create.blade.php``` )_ .  
Plak dit formulier in een nieuw bestand: **form.blade.php** .    
In het `create` bestand moet je nu aangeven dat je het formulier wilt includen, hierbij is het handig als je de route en post methode mee geeft zodat je het formulier op twee verschillende manieren kunt gebruiken.  
Dit kun je doen als volgt waarbij ik als 2e parameter een array met waardes mee geef.:
```php
@include('dashboard.projects.form', ['route'=>route('projects.store'), 'method'=>'post'])
```
Omdat je volgens de browser alleen GET en POST methodes hebt moet ik een omweg gebruiken, daarom ziet het begin van het formulier na het verwerken er als volgt uit:
```php
{% raw %}
<form action="{{$route}}" method="post">
    @csrf
    {{ method_field($method) }}
{% endraw %}
```

---
### 3- De edit view
Kopieer nu het `add.blade.php` of als je die niet hebt, `create.blade.php` bestand naar `edit.blade.php` en pas daar onder andere de titel aan zodat het duidelijk is dat je een project gaat aanpassen.  
Ik heb bijvoorbeeld deze titel geplaatst: 
```php
{% raw %}Je gaat nu dit project bewerken: {{$project->title}}{% endraw %}
```
De route moeten wij ook even aanpassen omdat je nu iets gaat opslaan.  
In de lijst met routes heb je waarschijnlijk ook deze route gezien: `projects.update` Daar zie je ook dat de methode `put` is in plaats van `post`, dus die moet ik aanpassen bij het laden van het formulier.   
De include in de `edit.blade.php` ziet er daarom als volgt uit:
```php
    @include('dashboard.projects.form', ['route'=>route('projects.update', $project), 'method'=>'put'])
```

---
### 4- De edit functie
In de ProjectAdminController zoek je de edit functie op en zorg je dat het edit.blade.php bestand terug geeft met daarbij de je model als extra parameter:
```php
{% raw %}
    public function edit(Model $model)
    {
        return view('dashboard.model.edit', ['model'=>$model]);
    }
{% endraw %}
```

---
### 5- Meegeven van het project aan de velden
In het formulier is het wel zo fijn als de oude data zichtbaar is in de velden.   
Daarom gaan wij op de plekken waar wij nu de oude data weergeven als extra parameter de originele data van het project meegeven, _als default waarde_.
Een invul veld kan er daarom zo uit gaan zien:  
```php
{% raw %}<input id="title" name="title" type="text"
                value="{{old('title', $project->title)}}"
                class="block w-full rounded-md border-0">{% endraw %}
```
Bekijk het formulier maar eens en zie dat de informatie van het project zichtbaar is in het formulier.

---
### 7- Model ook meegeven bij het aanmaken
Zorg er voor dat je bij het includen van het formulier in de `create.blade.php` ook een artikel mee geeft zodat je geen error krijgt bij het aanmaken van een project.  
In de create.blade.php ziet mijn include er nu zo uit:
```php
@include('dashboard.projects.form', 
    [
        'route'=>route('projects.store'), 
        'method'=>'post', 
        'project'=>new \App\Models\Project()
    ]
)
```

---
### Optionele video:

{% include youtube.md video="NB0uzSPVJCk" title="Intro over login/dashboard linkjes"%}

---

{% include youtube.md video="P25y0UCOWLg" %}

Zorg dat je een link vanaf de lijst met gegevens naar de `edit` route en daar ene view hebt met een formulier.
Zorg dat je het formulier hergebruikt dat je al had gemaakt. Zorg ook dat de gegevens al worden ingevuld.
{: .text-blue-100 .fs-4 }

### Links

- [Blade directives @auth en @guest](https://laravel.com/docs/9.x/blade#authentication-directives)


In de [volgende stap](edit-update) ga je het formulier valideren en de gegevens opslaan.
{: .text-green-100 .fs-5 }

---

{% include commit_push.md %}


