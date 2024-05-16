---
title: Les 1
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Development omgeving starten
{: .text-green-100 .fs-6 }

We gaan in een Docker container een WordPress site starten.  
Deze omgeving gaan wij tijdens deze gehele module gebruiken.

## Requirements
{: .text-red-100 .fs-6 }
Er zijn een aantal vereisten aan dit project:
1. Je hebt een werkende Docker Desktop installatie.
2. De volgende poorten zijn niet in gebruik:
   - 80
   - 3310
   - 1089
3. Je hebt een werkende IDE waarmee je websites kunt ontwikkelen.

---
### 1- Docker container initialiseren
1- Maak een nieuwe repository aan in [GitHub](http://github.com/) voor **m8prog-wordpress**, zorg dat de repository _private_ is.  
2- Navigeer op je computer naar de folder waar je project straks komt te staan, _niet een nieuwe folder aanmaken_.   
3- [Clone je github project](https://git-scm.com/docs/git-clone) zodat je een nieuwe folder hebt die gekoppeld is aan git en waar straks je bestanden in komen.  
4- Start eerst [Docker Desktop](https://www.docker.com/products/docker-desktop/)  
5- Plaats de docker-compose.yml in de root van deze folder. [download](data/docker-compose.yml)  
6- Plaats het `.env.example` bestand in de root van deze folder. [download](data/env.example)  
7- Kopieer het `.env.example` bestand naar `.env` en vul in dit nieuwe bestand de database gegevens in die je zelf verzint.   
8- Start de docker containers.  
```shell
docker-compose up
```
_Voeg eventueel `-d` toe om de terminal vrij te geven na het opstarten (docker detach)_

---
### 2- Controle
Als het goed is heb je nu een nieuw WordPress project waar je in kunt gaan werken.  
Waarschijnlijk is de link naar jouw project: [http://localhost:80](http://localhost:80)  
Behalve als je dit zelf aangepast hebt in het `docker-compose.yml` bestand

---
{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Configuratie en testen](configuratie)
