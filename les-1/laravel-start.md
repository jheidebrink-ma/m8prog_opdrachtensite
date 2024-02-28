---
title: Les 1
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Laravel project starten
{: .text-green-100 .fs-6 }

We gaan Laravel installeren in een Docker omgeving.  
Deze omgeving gaan wij tijdens deze gehele module gebruiken.

---
### 1- Laravel project initialiseren
1- Maak een nieuwe repository aan in [GitHub](http://github.com/) voor **m7prog-laravel**  
2- Navigeer op je computer naar de folder waar je project straks komt te staan.  
3- Wij werken nu volgens de setup van [laravel.com](https://laravel.com/docs/10.x)  
4- Start eerst [Docker Desktop](https://www.docker.com/products/docker-desktop/)  
Je kunt Laravel installeren op **twee** manieren, met een nieuwe docker installatie via **curl** of via **composer**. 
Begin met de eerste versie, gaat dit mis, dan kun je overstappen op het alternatief vanuit docker. 

### 2a- Installatie via Curl
Navigeer naar je project folder en voer het volgende commando uit in de terminal. Zo initialiseer je een nieuw laravel project in de folder **m7prog-laravel**:  
```curl -s "https://laravel.build/m7prog-laravel" | bash```  
Navigeer nu naar de folder m7prog-laravel  
```cd m7prog-laravel```  
Je kunt nu Laravel starten door gebruik te maken via Sail  
```./vendor/bin/sail up```  

### 2b- Alternatief via composer
Als alternatief kun je ook Laravel installeren via Composer.  
Hiervoor dien je composer op je computer geïnstalleerd te hebben, dit controleer je door `cmd` of de `terminal` te openen en dit commando uit te voeren:  
```composer -V```  
Zie je nu een error, dan moet je eerst composer installeren via: [https://getcomposer.org/doc/00-intro.md](https://getcomposer.org/doc/00-intro.md)  
Vervolgens ga je naar je project folder en installeer je laravel met dit commando:  
```composer create-project laravel/laravel m7prog-laravel```  
Nu kun je het project via docker starten.  
Kopieer de volgende folders uit de vorige les of download ze hieronder en plaats ze in deze ( **m7prog-laravel** ) folder:  
- /docker/ ( [download](docker.zip) )
- /docker-compose.yml ( [download](docker-compose.yml) )

Navigeer nu naar de folder **m7prog-laravel**<br>
Start docker:<br>
```docker-composer up -d```



---
### 3- Controle
Als het goed is heb je nu een nieuw Laravel project waar je in kunt gaan werken.

- Zorg ervoor dat je een git repo gekoppeld hebt aan dit project.  
- Je kunt de url terug vinden door in docker desktop te bekijken welke docker container er aan staat. Klik dan op de `NGINX` of `Laravel-test` container.  
- Wil je een `php artisan` commando uitvoeren dan moet je gebruik maken van de `php` of `Laravel-test` container.


---

{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Configureer je Laravel project](laravel-config)
