---
title: Les 5 
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Migration terug draaien
{: .text-green-100 .fs-6 }

In mijn project database heb ik te weinig velden toegevoegd. Ik wil namelijk ook nog een images veld toevoegen.

---
### 1- Rollback
Gebruik het volgende commando om de laatste migratie terug te draaien:
```shell
// Wanneer je gebruik maakt van de originele docker setup
php artisan migrate:rollback
```
```shell
// wanneer je gebruik maakt van `sail`
sail artisan migrate:rollback
```

---
### 2- Migratie aanpassen
Pas nu je migratie document aan door bijvoorbeeld een image veld aan te maken waar je straks de naam van een afbeelding kunt opslaan:  
```shell
    $table->string('image')->nullable();
```

---
### 3- Uitvoeren
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

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[CRUD operaties met je model class](crud-eloquent)


