---
title: Les 5
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Lijst weergave maken met de dashboard layout
{: .text-green-100 .fs-6 }

Nu ga je eerst de lijst view maken met de dashboard layout
Ook laat je een simpele lijst zien met de gegevens en paginering.

Later ga je daar edit-linkjes aan toevoegen zodat je elke rij uit de database kunt gaan aanpassen.

---

### 1- Menu aanmaken
Zoek in de web.php welke view er gebruikt is voor de dashboard pagina.

Dit is het onderdeel van het huidige dashboard menu item:
{% raw %}
```php
<x-nav-link :href="route('dashboard')" :active="request()->routeIs('dashboard')">
    {{ __('Dashboard') }}
</x-nav-link>
```
{% endraw %}

Zoek nu via php artisan op welke view er naar het projecten overzicht in het dashboard gaat met dit commando:

```shell
php artisan route:list
```

Kopieer de naam en plaats deze in het nieuwe menu item dat je gemaakt hebt.

Let op, er is ook een hamburger menu, onderaan, daar is het ook handig om het menu item toe te voegen.

---

### 2- Dashboard view folder
Maak in de **views** folder een mapje `dashboard` plaats daarin een mak met de naam `projects` 

Kopieer de `dashboard.blade.php` naar deze nieuwe folder en noem hem `index.blade.php`  
Pas in dit bestand de titel aan zodat je weet naar welke view je kijkt.

Geef aan in de index functie van je controller aan dat je een view wilt weergeven.
Bijvoorbeeld met deze functie:
```php
return view('dashboard.projects.index');
```


---
### 3- Overzicht in je view 
In de view ga je nu een weergaven maken van je projecten.  
Haal eerst in de index functie de artikelen op en geef aan dat je gebruik wilt maken van paginering.  
Geef de 
{% raw %}
```php
$projects = Project::paginate(2);
return view('dashboard.projects.index', ['projects'=>$projects]);
```
{% endraw %}

In de view kun je nu alle projecten weergeven zoals je al eerder hebt gedaan.  
Daaronder kun je nu de paginering weergeven met deze code {% raw %}{{$projects->links()}}{% endraw %}
Dan krijg je bijvoorbeeld zo'n stuk code:
{% raw %}
```php
@foreach($items as $item)
    <a href="{{$item->title}}">{{ $item->title }}</a><br>
@endforeach
{{$items->links()}}
```
{% endraw %}
                    


---

### Optionele video:

{% include youtube.md video="KJqt5Y7fe_I" %}

In de volgende opdracht ga je zelf een formulier maken, validatie regels toevoegen en foutmeldingen tonen.
Daarna kun je de gegevens via je Model class makkelijk toevoegen aan de database
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


