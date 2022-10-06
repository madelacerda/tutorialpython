# Test Fullstack Tech-K

## Objetivo
---
Por medio de este test se evaluarán algunos de tus conocimientos que nos interesan como desarrollador.

## Instrucciones de uso
---
1. [Duplica](https://help.github.com/es/github/creating-cloning-and-archiving-repositories/duplicating-a-repository) el proyecto
2. Cambiar su [visibilidad](https://help.github.com/es/github/administering-a-repository/setting-repository-visibility) a privado
3. Agrega al usuario `techk-devs` como colaborador dentro del repositorio
4. Instalar cliente de [Docker](https://www.docker.com/)
5. Instalar [Docker Compose](https://docs.docker.com/compose/)
6. Levantar el proyecto:
    * `$ cd path/to/project/fullstack/techk`
    * `$ docker-compose up`
    * Verificar correcto funcionamiento en [http://localhost:8000/](http://localhost:8000/)
7. Desarrollar lo que se indica. Si existen supuestos, estos deben definirse claramente en el README
8. Notificar mediante email cuando este listo y enviar el link del repositorio privado.


## Instrucciones de desarrollo
---
Desarrollar un scraper que permita obtener información de [esta página web](http://books.toscrape.com/index.html), almacenarla en BBDD y luego visualizarla en una interfaz web.

Lo anterior será bajo el uso del framework [Django 2.0.13](https://www.djangoproject.com/).

### *Web Scraping*

Se requiere obtener del [sitio web](http://books.toscrape.com/index.html) la siguiente información:

* Listado de categorías (travel, mystery, etc.)
* Información de cada libro:
  * Category
  * Title
  * Thumbnail
  * Price
  * Stock
  * Product Description
  * UPC

***Nota:*** Se recomienda usar las librerías [Requests](http://docs.python-requests.org/en/master/) y [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) para resolver este punto.

### *Backend*

La información obtenida por el scraper (en la sección anterior) debe ser almacenada en una BBDD sqlite. Para ello se debe modelar la BBDD, crear los modelos de Django y sus respectivas migraciones.

### *Frontend*

La información obtenida por el scraper debe ser presentada en forma de tabla. El diseño queda a libre elección del desarrollador.

¿Qué considera?
* Un botón que inicie/ejecute el scraper para obtener los datos del sitio web(*)
* Un listado de Categorías obtenidas por el scrapers.
* Al seleccionar una categoría, la tabla sólo mostrará libros de esa categoría
* La tabla debe tener un buscador por los atributos que posee
* Se debe poder eliminar registros de la tabla que se presente

***Notas:***
(*): Si no se dispone de los datos obtenidos por el scraper, debido a la no realización de esta etapa, los datos deben ser cargados desde un archivo en formato json. Este archivo debe contener la información mínima para que la interfaz web funcione correctamente, es decir:
* Al menos 3 categorías
* Al menos 5 libros por categoría
* Estructura del archivo JSON es de la siguiente forma:
```
[{
    "categories": [
        {
            "id": 1,
            "name": "Travel"
        }, {
            "id": 2,
            "name": "Mystery"
        }, {
            "id": 3,
            "name": "Historical Fiction"
        }
    ],
    "books": [
        {
            "id": 1;
            "category_id": 1,
            "title": "It's Only the Himalayas",
            "thumbnail_url": "http://books.toscrape.com/media/cache/6d/41/6d418a73cc7d4ecfd75ca11d854041db.jpg",
            "price": "£45.17",
            "stock": true,
            "product_description": "Wherever you go, whatever you do, just ...",
            "upc": "a22124811bfa8350"
        }
    ]
}]
```

## Restricciones
---
* No se debe usar el Admin de Django
* Usar ORM de Django (no raw queries)
* Uso de `Django Rest Framework` para la comunicación entre frontend y backend
* Si entregas la prueba con un sólo commit, no la revisaremos. El correcto uso de GIT es importante para nosotros


## Bonus
---
* Uso de alguna librería en el frontend. Idealmente `Vue` o `React`
* Webscraping usando la librería `Requests` y `BeautifulSoup`
* Uso de test (unittest con [pytest](https://docs.pytest.org/en/latest/))


## En qué nos fijaremos
---
* Correcto uso del ORM
* Correcto modelamiento la BBDD
* Correcto uso de GIT (no 9999 commit, no 1 commit y textos de los commits acorde al contenido)
* Patrones de diseño
* Orden del código (nombres, identación, principio de única responsabiilidad, etc)
* Complejidad de la implentación (más simple es mejor)

