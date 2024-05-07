---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Gebruik van WP CLI
{: .text-green-100 .fs-6 }

Nu je WP CLI geïnstalleerd hebt is het tijd om het te gaan gebruiken.  
### Lees deze hele pagina, maar voer alleen stap 1 en 2 uit.
{: .text-red-100 .fs-4 }
Stap 4 is voor de volgende les.
{: .text-red-100 .fs-4 }

--- 
### Note
{: .text-red-100}
De toevoeging `--allow-root` is, zoals eerder aangegeven, alleen noodzakelijk als je WP via sudo uitvoert.


---
### 1- Geef alle plugins weer
Via WP CLI kun je diverse acties uitveren om je WordPress site te beheren.  
Zo kun je bijvoorbeeld een plugin installeren, verwijderen of activeren.  
Of een complete lijst ophalen van alle geïnstalleerde plugins:  
```shell
wp plugin list --allow-root
```
Zie voor meer commando's over de plugins: 
[WP CLI plugin list](https://developer.wordpress.org/cli/commands/plugin/list/)

---
### 2- Updaten van WordPress, Plugins en Thema's
Het updaten van een WordPress site kun je ook doen via de WP CLI interface.

#### Core
{: .text-green-100 .fs-3 }
Met het volgende commando kun je controleren of de WP core geupdate moet worden:
```shell
wp core check-update --allow-root
```
Met het volgende commando kun je de core updaten:  
```shell
wp core update  --allow-root
```
#### Plugins
{: .text-green-100 .fs-3 }
Voor het updaten van je **alle** plugins gebruik je dit commando:
```shell
 wp plugin update --all  --allow-root
```

#### Thema's
{: .text-green-100 .fs-3 }
Voor het updaten van je **alle** thema's gebruik je dit commando:
```shell
 wp theme update --all  --allow-root
```

---
### 3- Transients legen
Binnen WordPress kun he gebruik maken van Transients, hiermee kun je gegevens tijdelijk in de database opslaan om zo je site te versnellen.  
Dit is een database cache.  
[WP Transients](https://developer.wordpress.org/apis/transients/)
Om alle transients te verwijderen uit de database gebruik je dit commando:  
```shell
wp transient delete --all --allow-root
```

---
### 4- Search and replace
Binnen WordPress wil je wel eens iets zoeken en vervangen, bijvoorbeeld als je domein naam verandert.  
Je kunt een query in de database uitvoeren, maar daarbij heb je ook kans dat er onderdelen stuk gaan.  
Een veilige tool is `search-replace` van `WP CLI`  
De structuur van dit commando is:  
```shell
wp search-replace <old> <new> <table> --dry-run --all-tables
```
Er zijn verschillende toevoegingen, een paar zijn: 
`<old>`  
Dit is de string die je zoekt in de database  
`<new>`  
Dit is de nieuwe string in de database  
`[--dry-run]`  
Als je dit toevoegd wordt de database niet aangepast, zo kun je een commando testen  
`[--all-tables-with-prefix]`  
Wil je alleen speciale tabellen aanpassen?  
`[--all-tables]`  
Hiermee geef je aan dat alle tabellen binnen de database aangepast moeten worden.  

Als ik bijvoorbeeld mijn website live wil zetten dan verandert mijn domein naam van `localhost` naar `m8prog.nl`  
Daarvoor ga ik eerst een test doen, ik pas de database nog niet aan.  
```shell
wp search-replace localhost m8prog.nl --dry-run --allow-root
```
Ik zie nu wat er allemaal aangepast zou moeten worden.  
Om het zoeken en vervangen **echt** uit te voeren, moet ik hetzelfde commando uitvoeren, maar dan zonder `--dry-run`.  

---
### 5- Vertaling maken
Ook dit is een functie die je kunt uitvoeren met WP CLI.   
De structuur van dit commando is:  
```shell
  wp i18n make-pot path/to/your-plugin-directory
```
## Let op, je moet wel de correcte folder opgeven.
{: .text-red-100 .fs-5 }
Dit kan ongeveer jouw commando zijn _( THEMA_NAAM is dan jouw eigen thema )_:
```shell
wp i18n make-pot wp-content/themes/THEMA_NAAM --allow-root
```
![make-pot.png](images%2Fmake-pot.png)  
Je ziet nun in de thema folder een `languages` folder met daarin een *.pot file.  
Deze kunt je weer vertalen via PoeEdit of een online tool als:  
[Po editor](https://localise.biz/free/poeditor)



### Links
- [WP CLI handboek](https://make.wordpress.org/cli/handbook/guides/)
- [WP CLI command0's](https://developer.wordpress.org/cli/commands/)
- [WP CLI core commando's](https://developer.wordpress.org/cli/commands/core/)
- [WP CLI thema commando's](https://developer.wordpress.org/cli/commands/theme/)
- [WP CLI vertalignen commando's](https://developer.wordpress.org/cli/commands/theme/)
- [WP CLI zoeken en vervangen](https://developer.wordpress.org/cli/commands/search-replace/)
- [WP CLI Transients](https://developer.wordpress.org/cli/commands/transient/)

