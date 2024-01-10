---
title: Les 7
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Formulier maken en de gegevens opsturen
{: .text-green-100 .fs-6 }

Je gaat een formulier maken om nieuwe gegevens toe te voegen.
Je zorgt ook dat het formulier veilig wordt opgestuurd en dat de gegevens aankomen in de juiste method in je controller.

---
### 1- Knop maken naar create
Zoek via het `php artisan route:list` op wat de naam van de route voor het aanmaken van een project.
Kopieer die naam en maak in de `dashboard/projects/index.blade.php` een link naar deze route.
{% raw %}
```php
<a href="{{route('ROUTE-NAAR-CREATE')}}" class="bg-green hover:bg-green text-white font-bold py-2 px-4 rounded float-right">
    {{ __('New project') }}
</a>
```
{% endraw %}


---
### 2- View aanmaken op basis van de index
Kopieer de `dashboard/projects/index.blade.php` view naar `dashboard/projects/create.blade.php`   
Hier komt het formulier in. 
Open deze nieuwe view en pas de titel aan dat je weet dat dit het formulier is.  
Je kunt de inhoud van de content verwijderen.


---
### 3- View implementeren in de controller
Net zoals bij de index zorg je er nu voor dat de controller een view terug geeft in plaats van de tekst.


---
### 4- Formulier maken
In Tailwind zit de basis form functionaliteit, hiermee kunnen wij formulieren aanmaken in de views.  
Zie: [Tailwind UI forms](https://tailwindui.com/components/application-ui/forms/form-layouts)
In je tailwind.conf in de root van je project moet je hiervoor aangeven fat je gebruik wil maken van de tailwind plugin:
```php
    plugins: [forms],
```

Je kunt nu het voorbeeld formulier van Tailwind kopiëren of je maakt een nieuw HTML formulier aan.  
Denk hierbij aan de volgende elementen:
- form action="{% raw %}{{route('project.store')}}{% endraw %}" ( de route om het formulier op te slaan )
- form method="post" 
- input fields waarbij de name gelijk is aan de naam van je database veld
- submit button


#### Cross-site request forgeries
Formulieren in Laravel zijn beveiligd met tegen Cross-site request forgeries, mensen die jouw formulier nabootsen.
Voeg daarom `@csrf` toe in het formulier door dit net na het openen van het formulier te plaatsen.


---
### 5- Ontvangen
Dit formulier verstuur je nu naar de `store` route.  
In de functie die deze functie op opvangt zorg ik nu dat de verstuurde data zichtbaar is.
Plaats daarvoor een dump() in deze store functie. Als je wilt kun je alle verstuurde data weergeven met de volgende code:
```php
/**
 * Store a newly created resource in storage.
 */
public function store(Request $request)
{
    dump( $request->all() );
}
```


---
### 6- Link naar nieuwe pagina
Het is natuurlijk handig om ergens een knop te hebben om een nieuw project aan te maken. 
Dan is het wel zo netjes als je ervoor zorgt dat deze knop alleen toegankelijk is voor ingelogde gebruikers.  
Dat kun je als volgt doen:  
```html
@auth
    <a href="{{route('ROUTE-NAAR-CREATE')}}" class="bg-blue hover:bg-green text-white font-bold py-2 px-4 rounded">Nieuw Project</a>
@endauth
```


---

### Optionele video:

{% include youtube.md video="iANa0-eoJEI" %}

Zorg dat je vanaf je lijst pagina een knop hebt naar de 'create' route met het formulier om gegevens toe te voegen.
Zorg ook dat je het gecontroleerd dat het form oin de `store()` method van je controller aankomt!`
{: .text-blue-100 .fs-4 }

In de volgende stap ga je validatie regels toevoegen zodat je foutmeldingen kunt tonen bij incorrecte invoer.
{: .text-blue-100 .fs-4 }

### Links

- [Tailwind CSS form voorbeeld](https://tailwindcss-forms.vercel.app/)  (bekijk de source om te zien hoe je dit doet met Tailwind CSS)

---

{% include commit_push.md %}


