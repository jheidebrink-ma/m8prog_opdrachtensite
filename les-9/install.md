---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Installatie van WP CLI
{: .text-green-100 .fs-6 }

Het installeren en testen van WP CLI gebeurt in een paar korte stappen.  
Alle `terminal` commando's worden uitgevoerd in de `wordpress docker container`.

---
### 1- Installeer WP via Curl
Eerst installeren wij `WP` via `curl` door dit commando uit te voeren in de `terminal`:
```shell
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
```
Controleer nu of het gelukt is met dit commando:  
```shell
php wp-cli.phar --info
```
Als het goed is zie je geen foutmelding, maar wel informatie over onder andere de `WP-CLI version`.

---
### 2- Shortcut to wp
Het is onhandig om steeds `php wp-cli.phar` in te moeten tikken voordat je een commando kunt uitvoeren.  
Daarom verplaatsen wij deze naar een plek binnen je PATH folder. _( waar de terminal altijd in kijkt om commando's uit te voeren)_   
Dat die je met deze commando's:
```shell
chmod +x wp-cli.phar
mv wp-cli.phar /usr/local/bin/wp
```
Nu kun je `WP CLI` commandos's als volgt uitvoeren:
```shell
wp --info
```
Het kan echter zijn dat er een waarschuwing over een sudo user in beeld is, in dit geval moet je de volgende optie na elk commando invoeren:  
```shell
--allow-root
```

---
### 3- Controle en update
Bekijk maar eens of je de laatste versie en update indien noodzakelijk hebt met dit commando:
```shell
wp cli update
```

### Links
- [wordpress cli handbook](https://make.wordpress.org/cli/handbook/guides/installing/)

---
### Volgende stap:
{: .text-green-100 .fs-4 }
[Gebruik van WP CLI](usage)



