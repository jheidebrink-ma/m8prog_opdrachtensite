---
title: Les 1
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Laravel project starten
{: .text-green-100 .fs-6 }

Maak een nieuwe repository aan voor m10prog-laravel
Navigeer op je compouter naar de folder waar binnen je project straks komt te staan.
Wij werken nu volgens de setup van [laravel.com](https://laravel.com/docs/10.x)
Je kunt Laravel installeren voor docker met het volgende commando:
```curl -s "https://laravel.build/m10prog-laravel" | bash```
Als alternatief kun je ook Laravel installeren via Composer.
Hiervoor dien je composer op je computer geïnstalleerd te hebben, dit controleer je met dit commando:
```composer -V```
Zie je nu een error, dan kun je composer installeren via: https://getcomposer.org/doc/00-intro.md
Vervolgens ga je naar je project folder en installeer je laravel met dit commando
```composer create-project laravel/laravel m10prog-laravel```

Navigeer nu naar de folder m10prog-laravel
Na deze installatie kun je Laravel sail starten:
```./vendor/bin/sail up```

---

Als het goed is heb je nu een nieuw Laravel project waar je in kunt gaan werken.

- Voeg alles toe aan je repository met `git add .`
- Commit (met een goede commit message) en push nu je nieuwe project naar Github.


---

{% include commit_push.md %}


