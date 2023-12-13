---
title: Les 5
layout: page 
permalink: :path/:basename 
nav_exclude: true
---

## Layout implementatie
{: .text-green-100 .fs-6 }

Nu heb je verschillende onderdelen van je website en is het handig om onderdelen van de layout te gaan hergebruiken.

In andere projecten gebruikte je daarvoor de de include en require functionaliteit van php.

In Laravel kun je gebruik maken van een basis template waar je variabele objecten in gaat stoppen. 

## Yield
Er zijn twee verschillende manieren om deze implementatie te gebruiken. Wij gaan aan de slag met het `@yield` commando.
Zie voor meer informatie [https://laravel.com/docs/10.x/blade](https://laravel.com/docs/10.x/blade)

Wij gaan een master layout maken waar wij verschillende elementen gaan toevoegen. Elke template zal de master gaan extenden ( uitbreiden ).

## 4 stappen:
1. Maak een `master.blade.php` bestand aan in de folder `resource/views/layout/`
2. Plaats in deze pagina verschillende HTML onderdelen, zie een voorbeeld van een layout onderaan de pagina, deze niet gebruiken omdat hij niet werkt.    
    Belangrijk is dat je ergens aangeeft dat daar de content moet komen met deze code:    
    `@yield( 'content' )`
3. Open het project.blade.php view bestand en geef bovenin aan dat je de master wilt extenden door deze code te plaatsen:    
   `@extends( 'layouts.master' )`
4. Plaats op de plek waar je de content wilt weergeven de html tussen deze codes:  
`@section('content')`  
`@endsection`

## JavaScript
Dit zelfde systeem  kunnen wij ook met bijvoorbeeld JavaScript gebruiken door bijvoorbeeld deze code in `project.blade.php` te plaatsen:  
```javascript
    @section('scripts')
        <script>
            Console.log('Mijn script werkt');
        </script>
    @endsection
```

In de `footer.blade.php` kun je in de deze scripts ophalen met deze code:  
``
    @yield( 'scripts' )
``


---
## Voorbeeld

```html
<!doctype html>
<html lang="{{ app()->getLocale() }}">
<head>
    <meta charset="utf-8">
    <meta name="csrf-token" content="{{ csrf_token() }}">
    <meta name="dinges" content="inhoud">
    <title>@yield('page_title') | {{ config('app.name', 'MA-Site') }}</title>
    <link href="{{ asset('css/app.css?v='.config('app.version')) }}" rel="stylesheet">
</head>

<body>
<header-tag>
    @include('layouts.partials.header')
</header-tag>
<content-tag>
    @yield( 'content' )
</content-tag>
@include('layouts.partials.footer')
@include('layouts.partials.scripts')
</body>
</html>
```

---

{% include commit_push.md %}


