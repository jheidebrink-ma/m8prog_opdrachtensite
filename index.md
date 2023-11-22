---
layout: home
title: F3M8PROG - Laravel
nav_order: 0
has_toc: false
---

# Laravel - {{ page.title }}

Op deze website vind je de opdrachten en hulp-video's voor de unit F3M8PROG (Laravel) van de module Werken voor opdrachtgevers (F3M8 Werken voor opdrachtgevers).

Je krijgt jouw persoonlijke (lege) repository door op de blauwe knop te klikken.  
**Dit hoef je maar één keer te doen!**. Je maakt alle opdrachten en oefeningen in deze repository.

- Kies vervolgens je eigen naam. 
- Er wordt een repository gemaakt waar jij toegang tot krijgt.
- Deze repository clone je naar jouw computer.

[Jouw Laravel repository ophalen]({{ site.bap.assignment_url }}){: .btn .btn-blue }

---

## Opdrachten en ondersteunende video's

{% for lesson in site.data.lessons %}
{% assign today = "now"|date:"%Y%m%d" %}
{% assign lesson_date = lesson.datum|date:"%Y%m%d" %}

{% if lesson_date <= today or site.bap.skip_date_check%}
## Les {{ lesson.number }}:  {{ lesson.title }}
{: .text-blue-100 :}

{{ lesson.description }}

[Start](les-{{ lesson.number }} ){: .btn .btn-blue }
{% else %}
## Les {{ lesson.number }}:  {{ lesson.title }}
{: .text-grey-dk-000 :}

Deze les komt binnenkort online.
{% endif %}
---

{% endfor %}
