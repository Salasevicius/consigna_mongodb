#  Ejercicio CRUD Básico con MongoDB

##  Objetivo

Practicar las operaciones CRUD usando una colección de libros.

##  Estructura del Documento

-   **title** (string)
-   **author** (string)
-   **genre** (string)
-   **year** (number)
-   **stock** (number)

##  Crear Base de Datos

``` js
use library_db;
```

##  Consigna

1.  Insertar 5 libros.
2.  Consultar por género y rango de años.
3.  Actualizar stock y datos.
4.  Eliminar un libro.
5.  Entregar comandos en un archivo .md.

##  Comandos para resolver la consigna

### Insertar libros

``` js
db.books.insertMany([
  {"title":"Cien años de soledad","author":"Gabriel García Márquez","genre":"Realismo mágico","year":1967,"stock":12},
  {"title":"El túnel","author":"Ernesto Sabato","genre":"Novela psicológica","year":1948,"stock":8},
  {"title":"Rayuela","author":"Julio Cortázar","genre":"Novela experimental","year":1963,"stock":10},
  {"title":"Ficciones","author":"Jorge Luis Borges","genre":"Cuentos fantásticos","year":1944,"stock":6},
  {"title":"La casa de los espíritus","author":"Isabel Allende","genre":"Realismo mágico","year":1982,"stock":9}
]);
```

### Consultas por género y rango de año

``` js
db.books.find({genre:"Realismo mágico"});
db.books.find({year:{$gte:1960,$lte:1980}});
```

### Actualizaciones de stock

``` js
db.books.updateOne({title:"El túnel"},{$set:{stock:15}});
db.books.updateOne({title:"Rayuela"},{$set:{stock:20}});
```

### Eliminación

``` js
db.books.deleteOne({title:"Rayuela"});
```
