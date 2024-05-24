---
title: Les 4
layout: page
permalink: :path/:basename
nav_exclude: true
---


## De HTML pagina structuur
{: .text-green-100 .fs-6 }

Het is nu tijd om de html pagina in te delen.  
Je kunt hiervoor gebruik maken van een standaard template van bijvoorbeeld Bootstrap of een ander systeem dat je hebt gekozen tijdens de eerste les.  
In dit voorbeeld behandel ik [Bootstrap](https://getbootstrap.com).  
_Voor Bootstrap kun je later ook deze plugin gebruiken om meer functionaliteit toe te voegen: [wp-bootstrap-blocks/](https://wordpress.org/plugins/wp-bootstrap-blocks/)_    
### In een volgende les gaan wij de vormgeving optimaliseren. Voor nu is de structuur belangrijk.  
{: .text-orange-100 .fs-3 }
<br>

![website.png](images%2Fwebsite.png)

---
### 1- HTML body
Hier kun je diverse Bootstrap voorbeelden vinden: [Download Bootstrap Examples](https://github.com/twbs/bootstrap/releases/download/v5.3.3/bootstrap-5.3.3-examples.zip)  
Ik gebruik voor nu het voorbeeld [CDN-starter](https://github.com/twbs/examples/tree/main/starter/)  
Bekijk hier de complete HTML pagina: [index.html](data%2Findex.html)  

In de `index.php` plaats ik de basis HTML stuctuur van de content.  
Alleen het **body** gedeelte plaats in ik de `index.php`.
```html
<main class="container my-5">
    <h1 class="mt-5">Dit is mijn eerste titel</h1>
    <div class="col-lg-8 px-0">
        <p class="fs-5">
            Intro
        </p>
        <p>
            Content
        </p>
    </div>
</main>
```

---
### 2- HTML in de Header
Zoals je ziet in het HTML voorbeeld moet er ook in de **header.php** een stuk html toegevoegd worden.  
Deze code plaats ik in de `head` om **bootstrap css** te laden via een CDN: 
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet"
          integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
```

Daarnaast is een voorbeeld menu ook wel fijn, dat doe je door deze code te plaatsen:
```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <a class="nav-link active" aria-current="page" href="#">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Link</a>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button"
                       data-bs-toggle="dropdown" aria-expanded="false">
                        Dropdown
                    </a>
                    <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                        <li><a class="dropdown-item" href="#">Action</a></li>
                        <li><a class="dropdown-item" href="#">Another action</a></li>
                        <li>
                            <hr class="dropdown-divider">
                        </li>
                        <li><a class="dropdown-item" href="#">Something else here</a></li>
                    </ul>
                </li>
                <li class="nav-item">
                    <a class="nav-link disabled">Disabled</a>
                </li>
            </ul>
            <form class="d-flex" role="search">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success" type="submit">Search</button>
            </form>
        </div>
    </div>
</nav>
```

---
### 3- HTML in de footer
In de **footer.php** moet een **javascript** vanaf de CDN geladen gaat worden zodat bijvoorbeeld de dropdown gaat werken.  
Plaats deze onderaan in je footer, boven het afsluiten van de body en html.
```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
        crossorigin="anonymous"></script>
```

Om een footer element aan te maken plaats ik deze code in mijn footer:  
```html
<footer class="footer mt-auto py-3 bg-body-tertiary">
    <div class="container">
        <span class="text-body-secondary">Place footer content here.</span>
    </div>
</footer>
```
Vergeet niet om ook de `html` en `body` tag die je in de header hebt geopend af te sluiten in de footer.


---
### 4- Controleer
Bekijk je website nu in de browser, je hebt nu een complete website.

---

{% include commit_push.md %}