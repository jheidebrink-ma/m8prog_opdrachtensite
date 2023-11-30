---
title: Les 1
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Laravel project starten
{: .text-green-100 .fs-6 }

We gaan Laravel installeren in een Docker omgeving. Deze omgeving gaan wij tijdens dit gehele blok gebruiken.

1- Maak een nieuwe repository aan voor **m10prog-laravel** of gebruik de vorige repo **m10prog**<br>
2- Navigeer op je computer naar de folder waar binnen je project straks komt te staan.<br>
3- Wij werken nu volgens de setup van [laravel.com](https://laravel.com/docs/10.x)<br>
Je kunt Laravel installeren op twee manieren, met een nieuwe docker installatie via **curl** of via **composer**. Begin met de eerste versie, gaat dit mis, dan kun je overstappen op het alternatief vanuit docker.<br>
### Installatie via Curl
Navigeer naar je project folder en voer het volgende commando uit, initialiseer je een nieuw laravel project in de folder **m10prog-laravel**: <br>
```curl -s "https://laravel.build/m10prog-laravel" | bash```<br>
Navigeer nu naar de folder m10prog-laravel<br>
```cd m10prog-laravel```<br>
Je kunt nu Laravel starten door gebruik te maken via SaiL:
```./vendor/bin/sail up```<br>
<br>
### Alternatief

Als alternatief kun je ook Laravel installeren via Composer.<br>
Hiervoor dien je composer op je computer geïnstalleerd te hebben, dit controleer je door cmd/terminal te openen en dit commando uit te voeren:<br>
```composer -V```<br>
Zie je nu een error, dan kun je composer installeren via: [https://getcomposer.org/doc/00-intro.md](https://getcomposer.org/doc/00-intro.md)<br>
Vervolgens ga je naar je project folder en installeer je laravel met dit commando:<br>
```composer create-project laravel/laravel m10prog-laravel```<br>
Nu kun je het project via docker starten.<br>
Kopieer de volgende folders uit de vorige les naar deze ( **m10prog-laravel** ) folder:
- /docker/
- /docker-compose.yml

Navigeer nu naar de folder **m10prog-laravel**<br>
Start docker:<br>
```docker-composer up -d```



---

Als het goed is heb je nu een nieuw Laravel project waar je in kunt gaan werken.

- Zorg ervoor dat je een git repo gekoppeld hebt aan dit project.
- Je kunt de url project terug vinden door in docker desktop te bekijken welke docker container er aan staat.


---

{% include commit_push.md %}


