---
title: Les 10
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Exporteren van data
{: .text-green-100 .fs-6 }

Het kan handig zijn als je bepaalde elementen kunt exporteren, naar bijvoorbeeld een csv bestand zodat deze later voor statistieken gebruikt kan worden door een klant of een specialist.  
Daarom gaan wij nu aan de slag met de export mogelijkheid binnen ons Laravel project.  
Eerst gaan wij één enkel object exporteren, later zullen wij een query gebruiken.

---
### 1- De functie
Om te beginnen heb je een functie nodig die de export afhandelt.  
Begin met het openen van de controller die de functionaliteit gaat afhandelen. Ik heb net een nieuwe controller `ProjectDownloadController` aangemaakt, maar je kunt ook de `ProjectController` gebruiken.  
Binnen deze Controller heb ik een nieuwe functie aangemaakt, aan deze functie geef ik een Project Model als parameter mee zodat ik altijd weet dat er een Project beschikbaar is: 
```php
{% raw %}
public function download(Project $project)
{
    
}
{% endraw %}
```

Binnen deze functie kan ik op verschillende manieren een export aanmaken.   
Voor deze export maak ik gebruik van een interne callback functie. 

Eerst maak ik een filenaam voor de download aan en ik stel de headers in zodat de browser weet dat iets wil downloaden.
```php
{% raw %}
    $csvFileName = 'projects' . $project->title . '.csv';
    $headers     = [
        'Content-Type'        => 'text/csv',
        'Content-Disposition' => 'attachment; filename="' . $csvFileName . '"',
    ];
{% endraw %}
```

Voor het aanmaken van de inhoud van het bestand maak ik binnen deze functie een callback functie.  
Eerst maak ik een `header` regel aan ( de veldnamen ) daarna maak ik een nieuwe regel met `\n\r` en vervolgens geef ik de data weer.  
Aan de callback geef ik ook mee dat ik de variabele `$project` wil gebruiken binnen de functie.
```php
{% raw %}
    $callback = static function() use($project) {
        echo 'id,title,description';
        echo "\n\r";
        echo implode(',', [
                $project->id,
                $project->title,
                $project->description
            ]);
    };
{% endraw %}
```

Tenslotte is het tijd om dit terug geven als response:
```php
{% raw %}
    return Response::stream( $callback, 200, $headers);
{% endraw %}
```

Alles bij elkaar zal ongeveer deze functie geven:
```php
{% raw %}
/**
     * Download a single project in csv format 
     * 
     * @param Project $project
     * @return \Symfony\Component\HttpFoundation\StreamedResponse
     */
    public function download(Project $project)
    {
        $csvFileName = 'projects' . $project->title . '.csv';
        $headers     = [
            'Content-Type'        => 'text/csv',
            'Content-Disposition' => 'attachment; filename="' . $csvFileName . '"',
        ];

        $callback = static function() use($project) {
            echo 'id,title,description';
            echo "\n\r";
            echo implode(',', [
                    $project->id,
                    $project->title,
                    $project->description
                ]);
        };

        return Response::stream( $callback, 200, $headers);
    }
{% endraw %}
```


### 2- route
Nu open je `web.php` en maak je een nieuwe route aan die deze functie aan roept.  
Bijvoorbeeld met zo'n route: _( dit zijn weer voorbeeld namen, gebruik je eigen namen )_
```php
{% raw %}
Route::get('/project/{project}/download', [ProjectDownloadController::class, 'download'])
    ->name('project.download');
{% endraw %}
```

### 3- Download knop
Tenslotte hebben we natuurlijk ook nog een download knop nodig:
```php
{% raw %}
    <a href="{{route('project.download', $poject)}}">
        Download dit project
    </a>
{% endraw %}
```

---

### Geen optionele video.
Er is geen video voor deze les.

### Links

- [Responses](https://laravel.com/docs/10.x/responses)


---

{% include commit_push.md %}


