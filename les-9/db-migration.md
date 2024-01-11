---
title: Les 7
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Database migration maken voor file upload
{: .text-green-100 .fs-6 }

Je moet eerst een veld toevoegen oim straks de bestandsnaam in op te slaan.  Dat doe je door een nieuwe database wijziging (migration) te maken en het veld toe te voegen.  
Daarna gebruik je `php artisan migrate` om de wijziging door te voeren in de database.

{% include youtube.md video="6vnKESFnyk0" %}

Zorg dat je een database migration hebt gemaakt en dat je ene plek hebt om de file upload op te slaan.
{: .text-blue-100 .fs-4 }

---

{% include commit_push.md %}


