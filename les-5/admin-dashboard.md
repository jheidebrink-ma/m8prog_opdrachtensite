---
title: Les 5
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Admin routes maken en dashboard layout gebruiken
{: .text-green-100 .fs-6 }

Je kunt een *verzameling* routes (url's) onder een bepaalde *prefix* hangen.
Alle beheers pagina kunt je bijvoorbeeld allemaal onder `/admin` plaatsen in je route bestand.

Je krijgt dan bijvoorbeeld de routes:

`/admin` = Admin dashboard  
`/admin/blogs` = Overzicht alle blog artikelen  
`/admin/blogs/new` = Voor aanmaken nieuwe blog artikelen  
`/admin/blogs/1/edit` = Voor bewerken van blog met id 1  
`/admin/blogs/2/edit` = Voor bewerken van blog met id 2  
`/admin/users`  = Overzicht van alle gebruikers  
`/admin/.....` - Enzovoort. 

Alles begint dus met de *prefix* `/admin`
Je kunt daarom makkelijk in één keer alle routes met de prefix `/admin` afschermen zodat alleen admin gebruikers er nog bij kunnen.

---

**Kijk de video om te zien hoe dit werkt.**

{% include youtube.md video="2UtpkqmhmJc" %}

---

Zorg dat je een route group hebt voor jouw CMS / Admin functionaliteit en dat je hiervoor de dashboard view (met de app layout) gebruikt.  
Dan heb je al standaard een menu en uitlog functionaliteit. [Hier vind je die default bestanden](https://github.com/laravel/breeze/tree/1.x/stubs/default/resources/views) mocht je ze kwijt zijn.
{: .text-blue-100 .fs-4 }

---

### Links

- [Lees meer over resource controllers](https://laravel.com/docs/9.x/controllers#resource-controllers)
- [Lees meer over Route groups](https://laravel.com/docs/9.x/routing#route-groups)
- [Meer over route prefixes](https://laravel.com/docs/9.x/routing#route-groups)
- [Meer over authenticatie en routes afschermen](https://laravel.com/docs/9.x/authentication#protecting-routes)

{% include commit_push.md %}


