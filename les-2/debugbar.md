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
    - Open hiervoor docker-desktop en zoek de juiste php container op
    - Klik op de drie puntjes achter de naam en daarna op **open terminal**
2. Controleer of je op de juiste instance zit met het volgende commando: ```php -v```
3. Installeer de debugbar via composer: <br>
	```composer require barryvdh/laravel-debugbar --dev```
4. Om de debug bar aan of uit te zetten kun je in de **.env** file aangeven of je applicatie in debug mode zit: ```APP_DEBUG=true```
5. Mogelijk laad het systeem niet automatisch de debug bar, daarom moet je in de<br>
	**providers array** in de **config/app.php** aangeven dat de debug bar geladen moet worden. <br>
	Voeg daarom deze regel toe:<br>
   ```Barryvdh\Debugbar\ServiceProvider::class,```
6. Als je binnen laravel gebruik wilt maken van de debug functie om bijvoorbeeld een debug regel weer te geven dan moet je in de <Br>
	**config/app.php** de volgende regel aan het **facades** onderdeel toevoegen:<br>
	`'Debugbar' => Barryvdh\Debugbar\Facades\Debugbar::class,`
7. Ga nu weer naar je website en zie dat je onderaan de pagina een debug bar hebt.

{: .text-blue-100 .fs-5 }

{% include commit_push.md %}


