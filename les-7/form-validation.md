---
title: Les 5
layout: page
permalink: :path/:basename
nav_exclude: true
---

## Form validatie en foutmeldingen
{: .text-green-100 .fs-6 }

Nu wordt het tijd om de ingevulde gegevens te valideren, zodat er geen lege artikelen in de database kunnen komen (in mijn geval)
Je doet dit door validatie regels per invoerveld te bedenken en je gebruikt de `validate()` method van de `$request` om de validatie uit te voeren.

Is een veld niet goed ingevuld dan stuurt Laravel je automatisch terug naar het formulier, zodat je de foutmelding(en) kunt tonen. Ook kun je de oude invoer weer in het veld zetten zodat je het niet opnieuw hoeft in te vullen.


{% include youtube.md video="az8ZV_XQJmI" %}

Zorg dat je een formulier hebt met validatie regels en foutmeldingen en dat de "oude" inpout were wordt getoond als er validatie errors zijn, zodat je niet alles opnieuw hoft in te vullen.
{: .text-blue-100 .fs-4 }

### Links
- [Documentatie over requests](https://laravel.com/docs/9.x/requests)
- [Documentatie over form validatie](https://laravel.com/docs/9.x/validation)
- [Alle validatie regels](https://laravel.com/docs/9.x/validation#available-validation-rules)
- [Documentatie over foutmeldingen tonen ](https://laravel.com/docs/9.x/validation#quick-displaying-the-validation-errors)
- [Documentatie over tonen van eerdere invoer](https://laravel.com/docs/9.x/requests#old-input)

---

{% include commit_push.md %}


