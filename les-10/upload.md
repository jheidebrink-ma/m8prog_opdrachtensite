---
title: Les 10
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Uploaden van je database, media bestanden, thema en plugins
{: .text-green-100 .fs-6 }

Je bent er bijna, nu ga je jouw lokale website in productie brengen.  
Eerst de database en dan de bestanden _( het mag ook andersom of tegelijk )_

---
### 1- Importeren van de database
1- Ga nu naar de admin omgeving van jouw **online** database.  
Bijvoorbeeld: [https://mediacollege-hosts-st1.cust.webslice.eu/ma-pma/](https://mediacollege-hosts-st1.cust.webslice.eu/ma-pma/)
Login met je database gegevens.  
In het geval van `ma-cloud` zijn dit de gegevens uit je `wp-config.php`  
2- **Verwijder** alle tabellen uit deze online database  
3- **Importeer** de tweede database dump.  
Met een beetje geluk werkt alles perfect, anders moet je eerst de dump aanpassen zodat deze geïmporteerd kan worden.  
_Ik moest overal ` COLLATE=utf8mb4_unicode_520_ci` verwijderen uit de dump._  

---
### 2- Uploaden van de media bestanden
Upload alle folders uit je `uploads` folder van jouw omgeving naar de `uploads` folder op de `ftp server`.

---
### 3- Uploaden van de plugins
Upload alle folders uit je `lokale plugins `omgeving naar de `plugins` folder op de `ftp server`.

---
### 4- Uploaden van je custom thema
Upload het de `custom thema` folder vanaf jouw lokale omgeving naar de `themes` folder op de `ftp server`.

---
### Volgende stap:
{: .text-green-100 .fs-4 }  
[Controle van je website](check)