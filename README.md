# Documentació Projecte
## Instalem l'entorn virtual
- Amb aquesta comanda instalem l'entorn virtual:
  ```python -m venv .venv```

- Amb aquesta comanda activem l'entorn virtual:
 ```.venv\Scripts\activate```

- Amb aquesta comanda instalarem tots els requeriments nesesaris:
 ```pip install -r requirements.txt```

##  Pugem tot al GitHub
- Primer entrem al entorn virtual
 ```.venv\Scripts\activate```

- Si no ho has sincronitzat abants utilitzem aquesta comanda:
  ```git remote add origin https://github.com/PolFerret05/psychic-octo-sniffle.git```

- Si ja ho has sincornitzat fem el següent:

- Utilitzem aquesta comanda per pasar de Local a la area de probes:
  ```git add * ``` o ```git add <fitxers>```

- Despres per pasar de l'area de probes al repositori local utilitzem aquesta comanda:
```git commit -m "missatge"```

- Per acabar pasarem del repositori local al Github ho fem amb aquesta comanda:
```git push origin master```


# Interació 1:
El primer que hem fet es modificar el fitxer "index.html" per que es pugui agafar dos categories més, ho he fet afegin aquestes linies:
```html
<li><a href="/lavanguardia/economia">Economia</a></li>
<li><a href="/lavanguardia/cultura">Cultura</a></li>
```
Les he afegit dintre de una llista en la cual estaven les altres categories.
Comprovació pagina "index.html":

![lsala](https://github.com/PolFerret05/psychic-octo-sniffle/blob/master/captura1.png)

Després dins de la carpeta rss/lavanguardia he creat un fitxer xml per a cada categoria, els fitxer s'anumenen economia.xml i cultura.xml. Dins dels fitxers he copiat el contingut xml dels rss de la vanguardia.

I per que es mostri per pantalla el contingut del xml modifiquem el fitxer lavanguardia.html afegint aquestes linies:
```html
<a href="{{ rss.feed.image.link}}"><img src="{{ rss.feed.image.url }}" alt="{{ rss.feed.image.title}}"></a> <!-- Aqui agafem el logo i fem que sigui un enllaç cap a la pagina wep del diari-->
{% for item in rss.entries %}
  <p>
      <a href="{{item.link}}">{{item.title}}</a> <!--Aqui agafem el link a la pagina de la noticia-->
      {% for media in item.media_content %}
          <p><img src="{{media.url}}" alt="{{item.title}}" /></p> <!--Aqui agafem la imatge de la noticia-->
      {% endfor %}
  </p>
  <p> Descipcion noticia - {{item.description}}</p> <!-- Aqui agafem la descripció de la noticia -->
  <p> Datos de creacion - {{item.published}}</p> <!-- Aqui agafem les dades de creacio de la noticia -->
  <p> Datos de modificacion - {{item.updated}}</p> <!-- Aqui agafem les dades de modificació de la noticia -->
  <p> Nombre del autor - {{item.author}}</p> <!-- Aqui agafem el nom del autor de la noticia -->
  <p> Categoria - {{item.category}}</p> <!-- Aqui agafem la categoria de la noticia -->
{% endfor %}
```

# Interació 2:
Primer de tot hem d'activar el Boostrap a totes les pagines en el que l'utilitzarem, i es fa posant aquestes linies:
Aquesta al <head>:
```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
```
I aquesta al final del <body>:
```html
     <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
     integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
     crossorigin="anonymous"></script>
```
## Barra de navegació
Un cop acivat per fer la barra de navegació he utilitzat aquest codi, la cual ha d'estar en totes les pagines:
```html
<nav class="navbar navbar-expand-sm bg-success navbar-dark sticky-top"> <!-- Aqui he posat que la lletra sigui blanca, que el fons sigui verd, la mida-->
  <div class="container-fluid">
    <a class="navbar-brand">La Vanguardia</a> <!-- Aqui he posat el nom del diari-->
    <div class="collapse navbar-collapse" id="collapsibleNavbar">
      <ul class="navbar-nav"> <!-- Aqui he fet una llista horitzontal amb links de totes les seccions-->
        <li class="nav-item">
          <a class="nav-link" href="/lavanguardia/deportes">Deportes</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/lavanguardia/politica">Política</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/lavanguardia/vida">Vida</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/lavanguardia/economia">Economia</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/lavanguardia/cultura">Cultura</a>
        </li>
      </ul>
    </div>
    <a class="text-white"><u>Pol Ferret Crusat</u></a><!-- I aqui el nom del creador de la pagina "jo"-->
  </div>
</nav>
```
Resultat:
![lsala](https://github.com/PolFerret05/psychic-octo-sniffle/blob/master/barra-navegacio.png)

## Carousel
Per fer el carousel he utilitzat un codi que he trobat a la pagina facilitada pel professorat que era el seguent:
```html
<div id="carouselExampleCaptions" class="carousel slide">
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
  </div>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h5>First slide label</h5>
        <p>Some representative placeholder content for the first slide.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h5>Second slide label</h5>
        <p>Some representative placeholder content for the second slide.</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h5>Third slide label</h5>
        <p>Some representative placeholder content for the third slide.</p>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
```
El qual he modificat per que quedes com a mi m'interesava, he posat amb comentaris les modificacions:
```html
<div class="conitner">
      <div class="row"> <!-- Aqui faig que divideixi l'ample de la pantalla en 12 columnes-->
        <div class="col-2"></div> <!-- Aqui faig que agafi 2 de les 12 columnes per que estiguin amb blanc-->
        <div class="col"> <!-- Aqui faig que el carousel estigui dins de les columnes restants-->
           <div id="carouselExampleCaptions" class="carousel slide">
                <div class="carousel-indicators">
                  <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
                  <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
                  <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
                  <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="3" aria-label="Slide 4"></button>
                  <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="4" aria-label="Slide 5"></button>
                </div>
                <div class="carousel-inner">
                  <div class="carousel-item active">
                    <div>
                        <img src="/static/img/deportes.jpg"  class="d-block w-100" alt="Imagen del girona clasificado a la Champions League">
                    </div>
                    <div class="text-center d-none d-md-block text-black mt-5"> <!-- He modificat el "class" perque el text estigui fira de la imatge i configuracions del text, aixo en tots els textos del carousel-->
                      <h5>Girona a Champions</h5>
                      <p>El Girona FC se clasifica a la proxima edicion de la UEFA Champions League tras ganar al Barça 4-2.</p>
                    </div>
                  </div>
                  <div class="carousel-item">
                    <img src="/static/img/politica.jpg" class="d-block w-100" alt="Pedro Sánchez en Vilanova i la Geltrú">
                    <div class="text-center d-none d-md-block text-black mt-5">
                      <h5>Pedro Sánchez en Vilanova i la Geltrú</h5>
                      <p>Pedro Sánchez estuvo en Vilanova i la Geltrú participando en el miting del partido catalan PSC.</p>
                    </div>
                  </div>
                  <div class="carousel-item">
                    <img src="/static/img/vida.jpeg" class="d-block w-100" alt="Dani Alves sale de la carcel">
                    <div class="text-center d-none d-md-block text-black mt-5">
                      <h5>Dani Alves sale de la carcel</h5>
                      <p>Dani Alves sale de la carcel</p>
                    </div>
                  </div>
                  <div class="carousel-item">
                    <img src="/static/img/economia.jpeg" class="d-block w-100" alt="El paro sube">
                    <div class="text-center d-none d-md-block text-black mt-5">
                      <h5>El paro sube</h5>
                      <p> El índice de paro sube al 3,9%, pero bate un récord de cinco décadas al mantenerse 27 meses por debajo del 4%</p>
                    </div>
                  </div>
                  <div class="carousel-item">
                    <img src="/static/img/cultura.jpeg" class="d-block w-100" alt="Nuevo ministro de cultura">
                    <div class="text-center d-none d-md-block text-black mt-5">
                      <h5>Nuevo ministro de cultura</h5>
                      <p> La Conselleria de Cultura, en manos de Vox, se adhiere a la propuesta de Extremadura “para proteger la existencia de este galardón” mientras acusa al Gobierno de ”sectarismo político"</p>
                    </div>
                  </div>
                </div>
                <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
                  <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
                  <span class="carousel-control-next-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Next</span>
                </button>
          </div>
        </div>
    <div class="col-2"></div><!-- Aqui faig que agafi 2 de les 12 columnes per que estiguin amb blanc i que el carousel estigui en el centre-->
    </div>
    </div>
```

## Modificació del arxiu lavanguardia.html
Modifiquem el codi afegin dos contenidors per que quedi tot ben estructurat
```html
<div class="row"> <!-- Aquest contenidor el que fa es estructurar tots els contenidors-->
  {% for item in rss.entries %}
    <div class="col-10 col-xxl-3 col-lg-4 border border-primary color"><!-- Aquest contenidor el que fa es posar la noticia en un contenidor amb bordes de color blau, i al estar dins del for(bucle) es repetira cada cop que es fagi, aixi totes les noticies ho tindran-->
      <p>
          <a href="{{item.link}}">{{item.title}}</a>
          {% for media in item.media_content %}
              <p><img src="{{media.url}}" alt="{{item.title}}" /></p>
          {% endfor %}
      </p>
      <p> Descipcion noticia - {{item.description}}</p>
      <p> Datos de creacion - {{item.published}}</p>
      <p> Datos de modificacion - {{item.updated}}</p>
      <p> Nombre del autor - {{item.author}}</p>
      <p> Categoria - {{item.category}}</p>
    </div>
  {% endfor %}
</div>
```
Resultat: 

![lsala](https://github.com/PolFerret05/psychic-octo-sniffle/blob/master/div-imatge.png)

# Extres:
## Afegir un altre diari
El primer que he fet es cambiar el nom al fitxer que es deia index.html a lavanguardiaindex.html, i he creat els fitxers elpuntavuiindex.html i el index.html.

En el fitxer elpuntavuiindex.html el que he fet es copiar el contingut del lavanguardiaindex.html i he cambiat els enllaços i el text per relacionar-ho amb el diari.

En el fitxer index.html he creat el seguent codi on hi ha el logo de cada diari el cual et porta a la pagina personal de cada diari, el de la vanguardia et porta al fitxer lavanguardiaindex.html i el del punt avui al elpuntavuiindex.html:
```html
<!DOCTYPE html>
<html lang="ca">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="/static/css/style.css">
      <!-- CSS del framework bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <title>Diaris!</title>
    <!-- <style>
        .texto1 {
            position:relative;
        }
    </style> -->
    <body class="color">

    <nav class="navbar navbar-expand-sm bg-success navbar-dark sticky-top">
      <div class="container-fluid">
        <a class="navbar-brand">Diaris</a>
        <a class="text-white"><u>Pol Ferret Crusat</u></a>
      </div>
    </nav>
    <h1 class="text-center">Tria un dels dos diaris:</h1>
    <div class="container-fluid ">
      <div class="row">
        <div class="col-6 text-center border border-primary p-5">
          <h1>La Vanguardia</h1>
          <a href="/indexlavanguardia"><img src="/static/img/lavanguardia.png" alt="Logo de La Vanguardia"></a>
        </div>
        <div class="col-6 text-center border border-primary p-5 ">
          <h1>El Punt Avui</h1>
          <a href="/indexelpuntavui"><img src="/static/img/elpuntavui.png" alt=""></a>
        </div>
      </div>
    </div>

     <!-- JavaScript del framework bootstrap -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
    crossorigin="anonymous"></script>
</body>
</html>
```
Resultat:
