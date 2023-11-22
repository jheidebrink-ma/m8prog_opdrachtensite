---
title: Les 4
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Overzicht: Models en de database
{: .text-green-100 .fs-6 }

**Zorg dat je deze introductie even rustig doorleest zodat je snapt hoe de model-laag in Laravel samenwerkt met de database.**

---

De *model* laag in een MVC-framework (zoals Laravel) bevat alle functionaliteit om met de gegevens in je website of
webapplicatie te werken.

Laravel bevat hiervoor twee belangrijke onderdelen:

1. De **QueryBuilder** waarmee je vrij "low-level" SQL queries kunt uitvoeren op de database.
2. **Eloquent**. Een onderdeel die het makkelijk maakt om alle CRUD-operaties (create, read, update en delete) en meer uit te
   voeren op de gegevens in je database.

Je kunt zelf kiezen welke manier je het prettigste vindt (maar Eloquent heeft veel meer voordelen en mogelijkheden).

---

### QueryBuilder

De QueryBuilder is een simpele manier om met gegevens uit je database te werken. Deze code laat zien hoe je alle
users ophaalt uit de `users` table (bijvoorbeeld in een controller method):

```php
// Bovenin je PHP file moet je altijd aangeven wat je bedoelt met DB
use Illuminate\Support\Facades\DB;

// En dan bijvoorbeeld in een listUsers() function in een controller
public function listUsers(){
    $users = DB::table('users')->get(); 
    
    // $user bevat een array met alle rijen uit de users table
    foreach ($users as $user) {
        echo $user->name;
    }
}
```

Om een rij aan de `users` table toe te voegen (insert) gebruik je de `insert()` method van de `DB` class:

```php
// Bovenin je PHP file moet je altijd aangeven wat je bedoelt met DB
use Illuminate\Support\Facades\DB;

// En dan bijvoorbeeld in een insertUser() function in een controller
public function insertUser(){
   DB::table('users')->insert([
       'name' => 'Dylan',
      'email' => 'dylan@example.com',
   ]);
}
```

Uiteraard kun je ook gegevens verwijderen en updaten. Lees hoe je dat doet in [de QueryBuilder documentatie](https://laravel.com/docs/9.x/queries).
Of kijk hier voor [een eerdere video opdracht](http://bap.mediadeveloper.amsterdam/md2/laravel/database-queries-in-laravel/) die ik heb gemaakt over de QueryBuilder voor MD2

---

### Eloquent

Wij gaan **Eloquent** gebruiken om met gegevens uit de database te werken.

- In Eloquent wordt elke table uit de database gekoppeld aan een PHP (model) class.
- Een class bevat de eigenschappen van de table en ook functions om met de gegevens te werken uit de database.


De PHP model classes staan altijd in: `app\Models`. Bijvoorbeeld `app\Models\User.php`:

```php
class User extends Model {
   // De User erft allerlei functions van de (Eloquent) Model class 
   // Hierdoor krijg je meteen al heel veel handige functionaliteit in je class!
}
```

Om deze User class (die in dit voorbeeld gekoppeld is aan de users table!) te gebruiken:

```php
// Altijd bovenaan aangeven welke model class je gaat gebruiken
use App\Models\User

// Zelfde voorbeeld als in vorige code maar dan met de Eloquent model class
public function listUsers(){
    $users = User::all(); // Via User class haal je alles uit de 'users' table
    
    // LET OP, HET VERSCHIL MET DE QUERYBUILDER IS: 
    // In elke $user zit nu een instance van de User class (en dus geen array)
    foreach ($users as $user) {
        echo $user->name;
    }
}
```
---

Houd goed in gedachten: **De PHP CLASS IS GEKOPPELD AAN EEN DATABASE TABLE**.

![Eloquent en database](images/eloquent-overview.png)

[Alles over Eloquent staat in de documentatie](https://laravel.com/docs/9.x/eloquent)

---

In de volgende opdracht ga je zelf een database migratie en een model class genereren voor jouw website en deze gebruiken om gegevens op te halen en te tonen in je view.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


