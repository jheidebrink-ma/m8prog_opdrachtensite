---
title: Les 2
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Debug bar implementeren 
{: .text-green-100 .fs-6 }

Met de debug bar voor Laravel kun je controleren wat er goed of niet goed gaat in je project.<br>
Stap voor stap uitleg kun je hier vidnen:<Br>
[https://github.com/barryvdh/laravel-debugbar](https://github.com/barryvdh/laravel-debugbar)

---

## Installatie
1. Login op de php docker container zodat je geen problemen hebt met php en composer.
    - Open hiervoor docker en zoek de juiste container op
    - Klik op de drie puntjes achter de naam en open de terminal
3. Controleer of je op de juiste instance zit met het volgende commando: ```php -v`
4. Installeer de debuigbar via composer: ```composer require barryvdh/laravel-debugbar --dev```
5. Stel in je .env in dat de site in debug modes zit door deze regel in de .env te plaatsen: ```APP_DEBUG=true```
6. Mogelijk laad het systeem niet automatisch de debug bar, daarom moet je in de ``providers array`` in de ``config/app.php`` aangeven dat de debug bar geladen moet worde. Voeg daarom deze regel toe:
   - ```Barryvdh\Debugbar\ServiceProvider::class,```
7. Als je binnen laravel gebruik wilt maken van de debug functie om bijvoorbeeld een extra regel weer te geven dan moet je de volgende regel aan het ``facades`` onderdeel toevoegen:
   - ```'Debugbar' => Barryvdh\Debugbar\Facades\Debugbar::class,```
8. Ga nu weer naar je website en zie dat je onderaan de pagina een debug bar hebt.

{: .text-blue-100 .fs-5 }

{% include commit_push.md %}


