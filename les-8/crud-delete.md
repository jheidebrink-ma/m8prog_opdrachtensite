---
title: Les 8
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Gegevens verwijderen
{: .text-green-100 .fs-6 }

Je gaat een mogelijkheid maken om gegevens te verwijderen. Nu heb je alle CRUD operaties en dus een simpel CMS gemaakt voor gegevens op je website.
De data wordt verstuurd naar de route:
```shell
DELETE       dashboard/projects/{project} ........ projects.destroy › ProjectAdminController@destroy
```

---
### 1- Verwijderen link in de index.
Als het goed is heb je bij elk project in het dashboard nu een `a href` link naar de delete route.  
Dit gaat alleen niet werken met een a href omdat de request dan altijd een GET methode is.  
Daarom moet ik eerst een formulier aanmaken met daarbij de juiste route en methode, bijvoorbeeld:
```php
    {% raw %}<form action="{{route('projects.destroy', $project)}}" method="post">
                @csrf
                {{ method_field('delete') }}
                <button type="verwijder" class="rounded-md bg-orange">
                    Verwijder
                </button>
            </form>{% endraw %}
```

---
### 2- Verwijderen van een element
Deze route komt aan in de ProjectAdminController en dan bij de `destroy` method.
In deze functie zie je dat het project al wordt weergegeven, die kun je vervolgens met de methode `delete()` verwijderen.  
Daarna redirect ik terug naar de index, mijn code ziet er bijvoorbeeld zo uit:
```php
    /**
     * Remove the specified resource from storage.
     */
    public function destroy(Model $model)
    {
        $project->delete();
        return redirect(route('model.index'));
    }
```

---
### 3- Maken van meldingen.
Het is natuurlijk fijn om steeds meldingen te geven als je iets verwijdert.  
Aan de voorkant kun je daarvoor javascript gebruiken.  
Aan de achterkant kun je een melding meegeven bij de redirect:  
```php
    return redirect(route('projects.index'))->with('alert', 'Het item '.$project->title.' is nu weg.');
```
In de view kun je vervolgens deze melding ophalen als volgt:
```php
    @if (session('alert'))
        <div class="p-2 bg-yellow border-2 rounded">
            {{ session('alert') }}
        </div>
    @endif
```

---
## Feest moment
Je hebt nu een mooie CRUD applicatie gemaakt.  
Geniet van dit moment, sla goed op, **commit** EN **push** en ga even een rondje dansen. 
<div style="width:100%;height:0;padding-bottom:75%;position:relative;">
<iframe src="https://giphy.com/embed/kyLYXonQYYfwYDIeZl" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
</div>
</p>

---
### Optionele video:


{% include youtube.md video="H5psYYY0Beg" %}

### Links

- [Deleting models](https://laravel.com/docs/9.x/eloquent#deleting-models)

Zorg dat je de gegevens vanaf de lijst/overzichtspagina kunt verwijderen.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


