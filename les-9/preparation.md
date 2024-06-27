---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Voorbereiding
{: .text-green-100 .fs-6 }

Nu gaan wij ons project voorbereiden om in productie te brengen door alle stappen te doorlopen.  

---
### 1- FTP toegang
Je hebt als het goed is al ftp toegang tot deze omgeving, anders hierbij jouw gegevens:  
Protocol: SFTP  
Domain: mediacollege-hosts-st2.cust.webslice.eu  
Username: je **ma** gebruikersnaam  
Password: je **ma** wachtwoord  

---
### 2a- Basis WordPress installatie op de ma-cloud omgeving
Indien je geen gebruik maakt van ma-cloud kun je direct naar stap **2b** gaan.  

![ma-cloud.png](images%2Fma-cloud.png)
In dit voorbeeld maak ik gebruik van jouw eigen ma-cloud omgeving.
- Login op: [panel.ma-cloud.nl](https://panel.ma-cloud.nl/ispconfig/)
- Klik op `Sites`
- Vervolgens op `Available packages`
- Daarna op `WordPress`
- En nu op `Install this package`
- Geef een `subfolder` op, bijvoorbeeld `m8prog`
- Genereer een wachtwoord ( onthoud deze )
- Accepteer de licentie
- Installeer

Nu moet je even wachten totdat de package actief is.  
Als de package actief is dan is het goed mogelijk dat de versie WordPress te oud is en niet werkt, in dat geval moet je stap **2b** doorlopen.
Voordat je WordPress handmatig installeert moet je de database gegevens uit de `wp-config.php` die `online` staat wel even **lokaal** opslaan.  
Zo zien de database gegevens er **ongeveer** uit:
```php
/** The name of the database for WordPress */
define('DB_NAME', 'XXXXXXXXXX');

/** MySQL database username */
define('DB_USER', 'XXXXXXXXXX');

/** MySQL database password */
define('DB_PASSWORD', 'XXXXXXXXXX');

/** MySQL hostname */
define('DB_HOST', '127.0.0.1:3306');

/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8');

/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', '');
```

### 2b- Handmatige WordPress installatie op de externe omgeving
[Downloaden WordPress](https://nl.wordpress.org/download/) en upload alle bestanden via de **ftp** naar correcte (sub)folder op jouw server.
Nadat je alle bestanden hebt geupload en eventueel overschreven, open je de wp-config.php en plak je jouw oude database gegevens erin.  
Heb je geen `wp-config.php` dan hernoem je `wp-config-sample.php` naar `wp-config.php` en voer je daar de correcte database gegevens in.  

Ga nu naar de url van jouw WordPress installatie en voeg daar `wp-admin` achter, bijvoorbeeld: `https://XXXXXXXX.hosts2.ma-cloud.nl/m8prog/wp-admin/`  
Je kunt nu inloggen met de gegevens die je aan het begin van deze stap hebt ingevoerd.  
![wp-install.png](images%2Fwp-install.png)  
Je hebt nu een complete WordPress installatie.  

---
### 3- Database dump waarbij het domein vervangen is door het nieuwe domein
Hiervoor maak ik gebruik van `WP CLI`, ik doe dit in 4 stappen:  
1- Export eerst de huidige locale database, dit is het origineel:  
Ga naar [phpmyadmin](http://localhost:1089) en exporteer de complete database `wp_db`  
2- Pas het domein in de huidige lokale database aan.  
Als voorbeeld is mijn nieuwe domein: `m8prog.nl`. _Dit is niet jouw domein naam en zul je moeten aanpassen!_  
Het commando om te testen:  
```shell
wp search-replace "http://locahost" "https://m8prog.nl" --dry-run --allow-root
```  
Voer dit nu uit door de `--dry-run` te verwijderen.  
3- Exporteer weer de database, deze dump ga je straks uploaden naar productie.  
4- **Verwijder** alle tabellen uit de locale database  
5- **Importeer** de eerste database dump.  

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Uploaden van je database, media bestanden, thema en plugins](upload)
