---
title: Les 8
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Gegevens valideren en opslaan
{: .text-green-100 .fs-6 }

Je gaat het formulier valideren en wijzigingen opslaan.  
De data wordt verstuurd naar de route: 
```shell
PUT|PATCH    dashboard/project/{project} ......... project.update › ProjectAdminController@update
```

---
### 1- Verwerken van de input
Nu is het weer tijd om de input te verwerken.  
Dit lijkt heel erg op het aanmaken van een project.  
Ga naar de volgende functie: `ProjectAdminController@update`  
Kopieer nu de complete code uit het create stuk en plak deze in de update, zodat je de validatie functionaliteit hebt.  
Zorg er vervolgens voor dat je niet een nieuw element aan maakt, maar dat je het object uit de parameters update.  
Dit is mijn complete `update` functie in de admin controller:
```php
/**
     * Update the specified resource in storage.
     * 
     * @param Request $request
     * @param MyModel $modelObject
     * @return \Illuminate\Contracts\Foundation\Application|\Illuminate\Foundation\Application|\Illuminate\Http\RedirectResponse|\Illuminate\Routing\Redirector
     */
    public function update(Request $request, MyModel $modelObject)
    {
        $valid_data = $request->validate(
            [
                'title'       => 'required|max:255|unique:models_tabel,id,'.$modelObject->id,
                'intro'       => 'required',
                'description' => 'required',
                'active'      => 'nullable',
            ]
        );

        $modelObject->update($valid_data);
        $modelObject->save();
        
        return redirect( route('mymodel.show', $modelObject->id ) );
    }
```
**Note**: gebruik wel je eigen `model` en `variabele` en `tabel` naam.  
Omdat ik nu ga bewerken wil ik wel dat de **titel** `uniek` is door te controleren of er een regel in de database is met deze nieuwe titel **EN** dan mag het huidige project niet mee tellen.  
Vandaar dit stukje in de validatie:
```php
'unique:models_tabel,id,'.$modelObject->id
```

---
### 2- Verwijderen van duplicate code
Om je code netjes te houden verplaats ik nu het validatie gedeelte naar een losse functie binnen mijn class zodat deze maar één keer voorkomt.  
Bekijk hiervoor de video als je meer informatie nodig hebt.


---
### Optionele video:


{% include youtube.md video="tjRt9vD8tM8" %}

Zorg dat je de gegevens valideert en de foutmeldingen ziet, en dat de aangepaste gegevens goed worden opgeslagen in de database.
{: .text-blue-100 .fs-4 }

### Links

- [Include andere views](https://laravel.com/docs/9.x/blade#including-subviews)
- [Updaten van een model / rij in de database](https://laravel.com/docs/9.x/eloquent#updates)

---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }
In de [volgende opdracht](crud-delete) ga je de laatste CRUD-operatie maken: Delete (verwijderen van een rij uit de database).
[Gegevens verwijderen](crud-delete)
