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

Un cop acivat per fer la barra de navegació he utilitzat aquest codi:
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
