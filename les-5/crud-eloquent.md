---
title: Les 5 
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## CRUD operaties met je Eloquent model class
{: .text-green-100 .fs-6 }

Je hebt nu een Eloquent model class die gekoppeld is aan een database table.

Nu kun je heel makkelijk gegevens gaan toevoegen, lezen, aanpassen en verwijderen (CRUD) in Laravel.  
Je hoeft geen ingewikkelde SQL queries meer te schrijven, maar werkt via de PHP model class en de ingebouwde functions met de database.

--- 
## Data versturen via de controller.  
Wij gaan tijdelijk via de controller extra projecten toevoegen om iets meer data weer te kunnen geven, dit doen wij in 3 stappen.

### 1. Route aanmaken
Maak een nieuwe route aan in `routes/web.php`, bijvoorbeeld:
```php
    Route::get('/projects/add', [ ProjectController::class, 'add' ])->name('project.add');
```

### 2. Controller endpoint aanmaken
Deze nieuwe route moet natuurlijk wel ergens opgevangen worden, dat doe je in: `app/Http/Controllers/ProjectController.phpp`.  
Daar moet nu een `add` functie komen die de data gaat toevoegen.
```php
    public function add() {
        
    }
```

### 3. Project aanmaken
Met de volgende code kun je een model aanmaken en vervolgens toevoegen aan de database:
```php
    // Maak een model aan
    $model = new Model();
    // definieer de velden
    $model->field_one = 'mijn data';
    // sla het model op
    $model->save();
```

## Resultaat
Roep de nieuwe url op in je browser.

Als het goed is zie je een witte pagina.

Nu kun je in de database zien dat je een project is aangemaakt.



---

### Optionele video

In de video laat kun zien hoe je deze model class kunt gebruiken om alle gegevens in de table op te halen via de model class en hoe je die gegevens vervolgens aan de view kunt geven om ze te tonen.

Meer informatie: [Crud videos](crud)



---

Zorg dat je alle CRUD operaties hebt uitgeprobeerd en kan toepassen in je code.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


