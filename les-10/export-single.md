---
title: Les 10
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Exporteren van data
{: .text-green-100 .fs-6 }

Het kan handig zijn als je bepaalde elementen kunt exporteren naar bijvoorbeeld een csv bestand zodat deze later voor statistieken gebruikt kan worden.  
Daarom gaan wij nu aan de slag met de export mogelijkheid.  
Eerst gaan wij één enkel item exporteren, later zullen wij een query gebruiken.

---
### 1- De functie
Eerst maken wij een functie in de controller voor een download 
```php


    /**
     * @return \Symfony\Component\HttpFoundation\StreamedResponse
     */
    public function downloadAll()
    {
        $projects    = Project::all();
        $csvFileName = 'projects.csv';
        $headers     = [
            'Content-Type'        => 'text/csv',
            'Content-Disposition' => 'attachment; filename="' . $csvFileName . '"',
        ];

        $callback = static function() use($projects) {
            echo 'id,title,description';
            foreach ($projects as $project) {
                echo "$project->id,$project->title,$project->description";
                echo "\n\r";
            }
        };

        return Response::stream( $callback, 200, $headers);
    }
```

### 2- route
Nu open je `web.php` en maak je een nieuwe route aan die deze functie aan roept.  
Bijvoorbeeld met zo'n route: _( dit zijn weer voorbeeld namen )_
Route::get('/project/{project}/download', [ProjectController::class, 'download'])->name('project.download');
Route::get('/project/download', [ProjectController::class, 'downloadAll'])->name('project.download_all');

### 3- Download knop
Tenslotte hebben we natuurlijk ok nog een download knop nodig:
```php
{% raw %}
    <a href="{{route('project.download', $poject)}}">
        Download All
    </a>
{% endraw %}
```

---

### Geen optionele video.
Er is geen video voor deze les.

### Links

- [Responses](https://laravel.com/docs/10.x/responses)

Zorg dat je file upload veld werkt en dat je het bestand kunt opvragen in je controller met de `dd()` functie.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


