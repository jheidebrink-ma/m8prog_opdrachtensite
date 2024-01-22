---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## File verwerken
{: .text-green-100 .fs-6 }

Je gaat een het bestand verwerken en opslaan op de server.

---
### 1- Controleren op een image
Omdat dit veld niet verplicht is kunnen wij er niet vanuit gaan dat wij altijd een afbeelding moeten verwerken.
Hiervoor kun je de `empty()' van php gebruiken.
```php
if ( ! empty($image) ) {
```
In dit voorbeeld controleer ik of de afbeelding NIET leeg is, en als dit waar is dan ga ik de upload verwerken.  

---
### 2- Verplaatsen van de afbeelding.
De afbeelding staat nu in de tijdelijke folder van de server, die kan ik nu gaan verplaatsen naar de storrage fodler:
Hiervoor kun je een simpele actie van Laravel gebruiken:
```php
    $path = $request->file('FILE_NAME')?->store('FOLDER');
```
Bij **FILE_NAME** kun je nu de naam van het input field gebruiken.  
Bij **FOLDER** kun je een naam van de folder aangeven, in ons geval waarschijnlijk: `public/projecten`.  
In de `/storage/app` folder kun je dit bestand terug vinden.
Let op dat je ze ook in de public folder plaatst omdat de browser er anders niet bij kan.

---
### 3- Opslaan van het path.
Je krijgt nu het path van de afbeelding terug, die kunnen wij opslaan in de database:
```php
    $project->image = $path;
    $project->save();
```

---
### 4- Update action
Voeg deze code ook toe aan de update functie zodat ook daar het bestand opgeslagen kan worden.



Zie voor meer informatie over het opslaan:
[Storage in Laravel](https://laravel.com/docs/10.x/filesystem)


---

### Geen optionele video.
Er is geen video voor deze les.

Zorg dat je file upload veld werkt en dat je het bestand kunt opvragen in je controller met de `dd()` functie.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


