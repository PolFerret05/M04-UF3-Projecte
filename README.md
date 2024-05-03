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

Després dins de la carpeta rss/lavanguardia he creat un fitxer xml per a cada categoria, els fitxer s'anumenen economia.xml i cultura.xml. Dins dels fitxers he copiat el contingut xml dels rss de la vanguardia.
