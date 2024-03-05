---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Database migration maken voor file upload
{: .text-green-100 .fs-6 }

Je moet eerst een veld toevoegen in de database om straks de bestandsnaam in op te slaan.  
Dat doe je door een nieuwe database wijziging `migration` te maken en het veld toe te voegen via een script.  
Daarna gebruik je `php artisan migrate` om de wijziging door te voeren in de database.

---
### 2- De database
Wij gaan straks bestanden opslaan op de server, maar die willen wij ook weer kunnen uitlezen aan de voorkant de website doordat deze gekoppeld is met een project.    
Het is namelijk belangrijk dat je weet welke foto je op welk moment moet weergeven.
**Note:** Controleer eerst of je nog geen `image` row in je tabel hebt.  _Als je die wel hebt dan kun je deze stap over slaan._  

Een nieuwe migratie maak je via `php artisan` of als je met sail werkt, via `sail artisan`.
Gebruik daarvoor het volgende commando:
```shell
[php of sail] artisan make:migration migratie_naam
```
Bijvoorbeeld:
```shell
php artisan make:migration alter_table_add_image_col
```
Vervolgens open je deze nieuwe migratie, die je vind in de database/migrations/ folder.  
Met deze migratie gaan wij de products tabel aanpassen door er een image kolom bij te plaatsen.  
Open deze migratie, geef aan welke tabel je wilt aanpassen met deze code ```Schema::table```, dus niet ```Schema::create()```.  
Vervolgens voeg je het veld toe dat je wilt toevoegen. In dit geval zal de image naam een `string` zijn.  
Bijvoorbeeld zo, _let wel even op dat je de juiste tabel en veldnaam gebruikt_:
```php
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::table('TABLE_NAME', function (Blueprint $table) {
            $table->string('FIELD_NAME')->nullable();
        });
    }
```
Nu je de migratie hebt gemaakt moet je ook aangeven hoe je deze weer ongedaan kunt maken.  
Daarbij geef je weer aan welke tabel Laravel moet gebruiken en welke kolom er verwijdert moet worden:
```php
    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::table('TABLE_NAME', function (Blueprint $table) {
            $table->dropColumn('FIELD_NAME');
        });
    }
```

---
### 3- Migratie
Voer vervolgens deze migratie uit via `php artisan` of als je met sail werkt, via `sail artisan`.
```shell
php artisan migrate
```

---
### Optionele video:
{% include youtube.md video="6vnKESFnyk0" %}

---
{% include commit_push.md %}

---
### Volgende stap:
{: .text-green-100 .fs-4 }
In de [volgende stap](file-upload) ga je een file upload veld toevoegen aan je formulier.


