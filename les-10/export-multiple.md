---
title: Les 10
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Exporteren van data
{: .text-green-100 .fs-6 }

Je hebt nu de flow gemaakt voor een export naar csv bestand, nu gaan wij een export maken voor meerdere projecten.  
Deze is hetzelfde als de vorige export, maar nu met meerdere items.

---
### 1- De functie
Om te beginnen heb je een functie nodig die de export afhandelt, maak daarom een nieuwe functie aan.  
In mijn geval is dat `downloadAll`.  

Binnen deze functie plak ik de functionaliteit uit de andere download functie.  
Alleen het export gedeelte pas ik aan door de project weergave in een loop in te plaatsen.  
```php
{% raw %}
    foreach ($projects as $project) {
        echo implode(
            ',',
            [
                $project->id,
                $project->title,
                $project->description,
            ]
        );
        echo "\n\r";
    }
{% endraw %}
```

### 2- route
Nu open je `web.php` en maak je een nieuwe route aan die deze functie aan roept.  
Bijvoorbeeld met zo'n route: _( dit zijn weer voorbeeld namen )_
Route::get('/project/download_all', [ProjectDownloadController::class, 'downloadAll'])->name('project.download_all');

### 3- Download knop
Tenslotte hebben we natuurlijk ok nog een download knop nodig:
```php
{% raw %}
    <a href="{{route('project.download_all')}}">
        Download All
    </a>
{% endraw %}
```

---

{% include commit_push.md %}


