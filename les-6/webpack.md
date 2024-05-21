---
title: Les 6
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Webpack integreren met WordPress
{: .text-green-100 .fs-6 }

Deze les een stuk minder verschillende stappen, dus heb je meer tijd om een mooie website te maken.  
Om onze SASS en JavaScipt te compilen maak ik gebruik van `npm` in combinatie met `webpack` om de assets te renderen.  
{: .mb-0 }
## Let op, straks wordt er een **node_modules** folder gegenereerd, deze mag niet in git.
{: .text-red-100 .fs-4 .mt-2 .mb-4 }


---
### 1- Structuur
Eerst heb je een structuur nodig.  
Maak in je thema map een aantal folders en bestanden die je als basis nodig hebt:
- src/js _( dit is de locatie van je javascripts die niet minified zijn )_
- src/scss _( hierin staan je SASS bestanden )_
- package.json _( hier staat in welke packages er nodig zijn zoals een sass compiler  )_
- webpack.config.js _( hier zijn de functies gedefinieerd voor het compilen van de sass )_  
Je kunt een voorbeeld van dit pakket bestanden ook hier downloaden: [example](data%2Fexample.zip)

---
### 2- package.json
In de [package.json](data%2Fpackage.json) kun je aangeven hoe je project heet en wat de locatie van `webpack.config.js` is.  
Je vind ook diverse dependencies die nodig zijn voor het compilen van dit project.  
Daarnaast zie je ook welke scripts er zijn en welke actie die uitvoeren, bijvoorbeeld `dev`

---
### 3- webpack.config.js
In de [webpack.config.js](data%2Fwebpack.config.js) vind je de acties die uitgevoerd worden tijdens het compilen.  

---
### 4- Packages installeren
Het installeren van de packages doe je via `npm`.  
Navigeer daarvoor in de terminal naar je thema folder en voer het volgende commando uit:  
```shell
npm i
```
_( npm install )_
Je ziet nu een `node_modules` folder in je thema folder.  
### **Note:** Zorg ervoor dat je de node_modules in je `.gitignore` hebt staan zodat deze niet gepushed wordt naar je repo.
{: .text-red-100 .fs-4 }
  
---
### 5- Packages compilen
Om de `sass` en de `javascripts` te compilen en in een `dist` folder te plaatsen kun je het volgende commando uitvoeren:  
```shell
npm run dev
```

---
### 6- Scripts toevoegen aan de website 
Voor het laden van de `javascripts` en `styles` maak je binnen WordPress gebruik van een **enqueue functie**.  
Zie voor de `scripts`: [https://developer.wordpress.org/reference/functions/wp_enqueue_script/](https://developer.wordpress.org/reference/functions/wp_enqueue_script/)  
En voor de `styles`: [https://developer.wordpress.org/reference/functions/wp_enqueue_style/](https://developer.wordpress.org/reference/functions/wp_enqueue_style/)
Hierdoor worden ook eventuele dependencies geladen en worden de scripts op de juiste plek geladen.  
Let even goed op welke parameters er zijn.  
Plaats daarvoor deze code in je `functions.php`:
```php

function add_style_and_js() {
	wp_enqueue_script(
		'm8prog',
		get_template_directory_uri() . '/dist/js/main.js',
		[ 'jquery' ],
		'1.0.0',
		[
			'strategy'  => 'defer',
			'in_footer' => true,
		]
	);

	wp_register_style(
		'm8prog_styles',
		get_template_directory_uri() . '/dist/css/main.min.css',
		[],
		'1.0.0'
	);
	wp_enqueue_style( 'm8prog_styles' );
}

add_action( 'wp_enqueue_scripts', 'add_style_and_js' );
```

---
### 7- Thema opruimen 
Omdat je nu gebruik maakt van de `wp_enqueue_script` en `wp_enqueue_style` hoef je de style en scripts niet meer los te laden in je header en footer.  
Mocht je dat nog wel doen dan moet je die regels verwijderen.

---
### 8- Controleer
Bekijk je website nu in de browser.  

---
### 9- Customize 
Pas nu de `scss` en templates nu aan zodat de website voldoet aan de eisen van jouw project.

---

{% include commit_push.md %}


