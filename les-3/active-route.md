---
title: Les 3
layout: page
permalink: :path/:basename
nav_exclude: true
---

## De actieve route een andere class/stijl geven
{: .text-green-100 .fs-6 }

Laravel is zo "slim" dat het weet welke route de bezoeker van je website op dit moment bezoekt.
Daarmee kun je de huidige menu optie een andere stijl geven.  
Ook gaan we de navigatie in een aparte template zetten en deze inladen met de `@include` instructie van de Blade template engine.
Zo is de navigatie ook makkelijker in andere layouts te gebruiken als je dat wilt.

---
### 1- Navigatie template
Als het goed is heb je een `navigation.blade.php` view in de `resources` folder.  
Het kan zijn dat dit document begint met een underscore, of dat je gebruik maakt van het dashboard voorbeeld.  
Open dit document en zoek je navigatie items op, dit ziet er bijvoorbeeld zo uit:
```php
{% raw %}
<x-nav-link :href="route('about')">
    {{ __('About') }}
</x-nav-link>
{% endraw %}
```
Of dat het er zo uit ziet:
```php
{% raw %}
<li class="mr-3 bg-lightblue text-white">
    <a href="{{ route('about') }}">
        {{ __('About') }}
    </a>
</li>
{% endraw %}
```

---
### 2- Active status
Als je de `<x-nav `oplossing gebruikt dan wordt de link afgehandeld in `resources/views/components/nav-link.blade.php`  
En hoef je alleen aan te geven wanneer dit element actief is door `:active="request()->routeIs('about')"` toe te voegen.  
Dit is dan het resultaat van mijn about link:
```php
{% raw %}
<x-nav-link :href="route('about')" :active="request()->routeIs('about')">
    {{ __('About') }}
</x-nav-link>
{% endraw %}
```

Werk je met optie 2 dan zul je dit in het link element aangeven via een if statement.  
Binnen Laravel kun je if statements maken op de volgende manier:  
```php
{% raw %}@if ( voorwaarde ) 
@endif {% endraw %}
```
In dit geval maak ik een if statement die controleert wat de huidige route is en dan de achtergrond een andere kleur geeft:  
```php
@if(request()->routeIs('about') 
    bg-blue 
@else 
    bg-white 
@endif
```

Het resultaat ziet er dan zo uit:
```php
{% raw %}
<li class="mr-3 bg-lightblue text-white @if(request()->routeIs('about') bg-blue @else bg-white @endif">
    <a href="{{ route('about') }}">
        {{ __('About') }}
    </a>
</li>
{% endraw %}
```

---
### Optionele video:
{% include youtube.md video="-W92U9ZVBZI" %}

---

Zorg dat je na het kijken van de video een werkend menu hebt en dat de actieve pagina een andere stijl heeft in het menu.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


