---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Gebruik van WP CLI
{: .text-green-100 .fs-6 }

Nu je WP CLI geïnstalleerd hebt is het tijd om het te gaan gebruiken.    

---
### 1- Geef alle plugins weer
Je kunt eenvoudig opvragen welke plugins

---
### 2- Search and replace
Binnen WordPress wil je wel eens iets zoeken en vervangen, bijvoorbeeld als je domein naam verandert.  
Je kunt een query in de database uitvoeren, maar daarbij heb je ook kans dat er onderdelen stuk gaan.  
Een veilige tool is `search-replace` van `WP CLI`  
De structuur van dit commando is:  
```shell
wp search-replace <old> <new> <table> --dry-run --all-tables
```
Er zijn verschillende toevoegingen, een paar zijn: 
**<old>**
Dit is de string die je zoekt in de database
<new>
Dit is de nieuwe string in de database
[--dry-run]
Als je dit toevoegd wordt de database niet aangepast, zo kun je eene commando testen
[--all-tables-with-prefix]
Wil je alleen speciale tabellen aanpassen?
[--all-tables]
Hiermee geef je aan dat alle tabellen binnen de database aangepast moeten worden.  

Als ik bijvoorbeeld mijn website live wil zetten dan verandert mijn domein naam van `localhost` naar `m8prog.nl`  
Daarvoor ga ik eerst een test doen, ik pas de database nog niet aan.  
```shell
wp search-replace localhost m8prog.nl --dry-run --allow-root
```
Ik zie nu wat er allemaal aangepast zou moeten worden.  
Om het zoeken en vervangen **echt** uit te voeren, moet ik hetzelfde commando uitvoeren, maar dan zonder `--dry-run`.  

---
### 3- Vertaling maken
Ook dit is een functie die je kunt uitvoeren met WP CLI.   
De structuur van dit commando is:  
```shell
  wp i18n make-pot path/to/your-plugin-directory
```
## Let op, je moet wel de correcte folder opgeven.
Dit kan ongeveer jouw commando zijn _( THEMA_NAAM is dan jouw eigen thema )_:
```shell
wp i18n make-pot wp-content/themes/THEMA_NAAM --allow-root
```
![make-pot.png](make-pot.png)
Je ziet nun in de thema folder een `languages` folder met daarin een *.pot file.  
Deze kunt je weer vertalen via PoeEdit of een online tool als:  
[Po editor](https://localise.biz/free/poeditor)




### Links
- [wordpress cli handbook](https://make.wordpress.org/cli/handbook/guides/)
- [Search and replace](https://developer.wordpress.org/cli/commands/search-replace/)

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Gebruik van WP CLI](usage)



