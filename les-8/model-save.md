---
title: Les 8
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Gegevens opslaan via je model class
{: .text-green-100 .fs-6 }

Nu de gegevens zijn gevalideerd kun je alle gegevens via je model class gaan opslaan in de database.  
Ook stuur je de gebruiker door naar een andere pagina na het opslaan, zodat je niet een dubbele rij in je table krijgt als je op reload drukt.

---
### 1- De valide data verwerken
Nu wij zeker weten dat de data goed is kunnen wij aan de slag met opslaan.  
Hiervoor ga je verder in de `store` functie in de `ProjectAdminController`.  
De dd() _`debug die()`_ functie heb je nu niet meer nodig, die regel kun je uit deze functie verwijderen.

Voor het aanmaken van een nieuw model weer drie manieren mogelijk:
### Optie 1:
```php
    $product = new Product::create($request->all());
```
### Optie 2:
```php
    $product = new Product($valid_data);
    $product->save();
```
### Optie 3:
```php
    $product            = new Product();
    $product->title     = $request->input('title');
    $product->category  = $request->input('category');
    $product->save();
```

Optie 1 en 3 zijn sneller, maar je hebt dan minder controle over de elementen.  
In optie 1 moet je eerst aangeven wat je wel en niet mag invullen, door in het model een protected $fillable array aan te maken.  
Dat doe je door in het model aan te geven welke elementen er ingevuld mogen worden.  
Bij mij ziet mijn Project model er nu zo uit:
```php
class Project extends Model
{
    use HasFactory;

    /**
     * Elements that are allowed be filled in directly
     *
     * @var string[]
     */
    protected $fillable = ['title', 'intro', 'description', 'active'];

    /**
     * The table associated with the model.
     *
     * @var string
     */
    protected $table = 'projects';
}

```

---
**Optie 3** is overzichtelijker en heb je al een keer gebruikt.   
In dit voorbeeld gaan wij gebruik maken van **optie 2**.    

---
### 2- Opslaan van de data
In ons geval hebben wij de informatie in de `$valid_data` variabele, waar alle elementen in staan die overeenkomen met de kolommen in de database.  
Hierdoor kun je op zo'n manier een nieuw model aanmaken en opslaan in de database:
```php
    $item = new Model( $valid_data );
    $item->save();
```
Door de `save()` functie aan te roepen wordt er een element toegevoegd aan de database. 

---
### 3- Versturen van resultaat
Als het item is opgeslagen kun je de gebruiker sturen naar een andere pagina met de volgende code:
```php
return redirect();
```
Geef als parameter de route mee waar je naartoe wilt.  
Bijvoorbeeld de `project.show` route met als parameter de id van het laatste element.
```php
return redirect( route('project.show', $project->id ) );
```


### Optionele video:

{% include youtube.md video="lsSiB1MG9o0" %}

Zorg dat je formulier helemaal werkt, met form validatie, foutmeldingen en een redirect na succesvol opslaan.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Aanpassen van gegevens met een formulier](form-edit)
