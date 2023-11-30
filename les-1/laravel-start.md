---
title: Les 1
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Laravel project starten
{: .text-green-100 .fs-6 }

Maak een nieuwe repository aan voor m10prog-laravel<br>
Navigeer op je compouter naar de folder waar binnen je project straks komt te staan.<br>
Wij werken nu volgens de setup van [laravel.com](https://laravel.com/docs/10.x)<br>
Je kunt Laravel installeren voor docker met het volgende commando:<br>
```curl -s "https://laravel.build/m10prog-laravel" | bash```
Navigeer nu naar de folder m10prog-laravel<br>
Na deze installatie kun je Laravel sail starten:<br>
```./vendor/bin/sail up```
<b>Alternatief</b>
Als alternatief kun je ook Laravel installeren via Composer.<br>
Hiervoor dien je composer op je computer geïnstalleerd te hebben, dit controleer je met dit commando:<br>
```composer -V```
Zie je nu een error, dan kun je composer installeren via: https://getcomposer.org/doc/00-intro.md<br>
Vervolgens ga je naar je project folder en installeer je laravel met dit commando<br>
```composer create-project laravel/laravel m10prog-laravel```
Nu moet je ervoor zorgen dat docker start.<br>
Kopieer de volgende folders uit de vorige les naar deze ( m10prog-laravel ) folder:
- docker<br>
- docker-compose.yml<br>
<br>
Navigeer nu naar de folder m10prog-laravel<br>
Start docker:<br>
```docker-compoer up -d```

---

Als het goed is heb je nu een nieuw Laravel project waar je in kunt gaan werken.

- Voeg alles toe aan je repository met `git add .`
- Commit (met een goede commit message) en push nu je nieuwe project naar Github.


---

{% include commit_push.md %}


