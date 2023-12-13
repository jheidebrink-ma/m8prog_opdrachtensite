---
title: Les 5 
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Migration terug draaien
{: .text-green-100 .fs-6 }

In mijn project database heb ik te weinig velden toegevoegd. Ik wil namelijk ook nog een images veld toevoegen.

### Rollback
Gebruik het volgende commando om de laatste migratie terug te draaien:
```shell
// Wanneer je gebruik maakt van de originele docker setup
php artisan migrate:rollback
```
```shell
// wanneer je gebruik maakt van `sail`
sail artisan migrate:rollback
```

### Migratie aanpassen
Pas nu je migratie document aan door bijvoorbeeld een image veld aan te maken:  
```shell
    $table->string('image')->nullable();
```

### Uitvoeren
Nu kun je de migratie opnieuw uitvoeren.
```shell
// Wanneer je gebruik maakt van de originele docker setup
php artisan migrate
```
```shell
// wanneer je gebruik maakt van `sail`
sail artisan migrate
```


---

{% include commit_push.md %}


