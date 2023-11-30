---
title: Les 2
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Tailwind implementeren
{: .text-green-100 .fs-6 }

[Tailwind CSS](https://tailwindcss.com/) kun je helemaal customizen met je eigen kleuren, stijlen, lettertypen en andere zaken.
<br>
Door gebruik te maken van Tailwind hebben wij met weinig moeite een responsive website ontwikkeld.<br>
<br>
Volg in deze installatie handleiding alleen stappen **1**, **2** en **3**: <br>
[Tailwind CSS installation](https://tailwindcss.com/docs/installation)
### Let op, de laatste twee stappen zijn voor ons anders:
#### Eerst implementeren wij de css in de header:<br>
Open welcome.blade.php in je resources/views folder en plaats de volgende regel in de head:<br>
`<link href="/dist/app.css" rel="stylesheet">`<br>
Het **\<style>\</style>** onderdeel kun je verwijderen.
<br>
#### Compile nu de css:
In de terminal kun je de css compile met dit commando:<br>
```npx tailwindcss -i ./resources/css/app.css -o ./public/dist/app.css --watch ```


---

Bekijk de website en zie dat je nu een complete site hebt met een responsive design.

{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


