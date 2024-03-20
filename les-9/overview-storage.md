---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Overzicht file uploads en storage in Laravel
{: .text-green-100 .fs-6 }

Overzicht hoe de file storage werkt in Laravel.

---
### 1- De upload folder
Binnen Laravel is een `storage` folder waar verschillende bestanden van het project opgeslagen worden. Denk hierbij aan:
- cache bestanden
- log bestanden
- bestanden die binnen het project geupload worden

Deze laatste gaan wij gebruiken om bestanden te uploaden.  
**Let op:** Deze folder staat niet in je `public` folder, en kan dus niet direct gebruikt worden door de browser.  
Gelukkig kan Laravel ons helpen om deze bestanden wel beschikbaar te maken op de public omgeving. 

### 2- Configuratie
In het bestand `config/filesystems.php` kom je verschillende instellingen tegen met betrekking tot het opslaan van de bestanden.  
Hier zie je bijvoorbeeld het onderstaande gedeelte:
```php
    'public' => [
            'driver' => 'local',
            'root' => storage_path('app/public'),
            'url' => env('APP_URL').'/storage',
            'visibility' => 'public',
            'throw' => false,
        ],
```
In dit onderdeel staat aangegeven wat de driver is, en bepaal je of je de bestanden lokaal op de server opslaat of op een externe server.    
Bij `root` kun je aangeven wat de locatie is van de folder op de server binnen de `storrage` folder.  
Bij `url` geef je aan wat de folder is in de browser, dit is zeg maar een alias naar de folder op de server.  

---

### Optionele video:

{% include youtube.md video="Dyie1Yw9HzE" %}

### Links

- [File storage in Laravel](https://laravel.com/docs/10.x/filesystem)

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Database migration maken voor file upload](db-migration)



