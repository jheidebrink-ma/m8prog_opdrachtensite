---
title: Les 2
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Tailwind configuratie aanpassen
{: .text-green-100 .fs-6 }

[Tailwind CSS](https://tailwindcss.com/docs/installation) kun je helemaal customizen met je eigen kleuren, stijlen, lettertypen en andere zaken.

Dit doe je in het bestand `tailwind.config.js` dat in de root van je Laravel project staat.
Als je Les 1 hebt gemaakt en Laravel Breeze hebt geïnstalleerd staat hier al wat configuratie in.

---

Je kunt alle onderdelen van het default theme *extenden* (uitbreiden) of onderdelen helemaal opnieuw instellen (zoals de kleuren, lettertypen e.d.)

Hier vind je de documentatie van de Tailwind configuratie:  

- [https://tailwindcss.com/docs/configuration#configuration-options](https://tailwindcss.com/docs/configuration#configuration-options)
- En hier [het basis Tailwind configuratie bestand](https://unpkg.com/browse/tailwindcss@3.0.24/stubs/defaultConfig.stub.js) met ALLES wat je kunt aanpassen of overschrijven.

---
Tailwind werkt anders dan bijvoorbeeld bootstrap. 
Tailwind kijkt naar jouw view bestanden ( templates ) om te zien welke styles en andere codes jij gebruikt in je bestanden. Alleen noodzakelijke css wordt gecompiled. 
Zo blijft de grote van je css minimaal.   
Hiervoor moet je wel in een terminal scherm Tailwind watch aan laten staan, met dit commando:
```shell
npx tailwindcss -i ./resources/css/app.css -o ./public/dist/app.css --watch
```

---

{% include commit_push.md %}


