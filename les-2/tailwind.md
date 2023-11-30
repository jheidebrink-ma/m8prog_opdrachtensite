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
Volg deze installatie handleiding: <br>
[Tailwind CSS](https://tailwindcss.com/docs/installation)
### Let op, de laatste twee stappen zijn voor ons anders:
#### Eerst implementeren wij de css in de juiste layout:<Br>
Open welcome.blade.php in je resources/views folder.<br>
Plaats de volgende regel in de head:<br>
```<link href="/dist/app.css" rel="stylesheet">```
<br>
#### Compile nu de css:
In de terminal kun je de css compile met dit commando:<Br>
```npx tailwindcss -i ./resources/css/app.css -o ./public/dist/app.css --watch ```


---

Bekijk de website en zie dat je nu een complete site hebt.

{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


