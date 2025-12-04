Ejercicio CRUD Básico con MongoDB --- Books Edition
Objetivo
Practicar las operaciones CRUD usando una colección de libros.

Estructura del Documento book
title (string)
author (string)
genre (string)
year (number)
stock (number)
1. Crear Base de Datos y Colección
use library;
2. Luego en todas las peticiones incorporar
db.books.metodo();
Consigna
Insertar 5 libros nuevos.
Consultar por género y por rango de años.
Actualizar el stock de 2 libros y los datos completos de 1 libro.
Eliminar 1 libro por título.
Entregar los comandos en un archivo .md.

COMANDOS NECESARIOS PARA LA REALIZACIÓN DE LA CONSIGNA:

1 - use library_db

2 - db.books.insertMany([{"title": "Cien años de soledad",
    "author": "Gabriel García Márquez",
    "genre": "Realismo mágico",
    "year": 1967,
    "stock": 12
  },
  {
    "title": "El túnel",
    "author": "Ernesto Sabato",
    "genre": "Novela psicológica",
    "year": 1948,
    "stock": 8
  },
  {
    "title": "Rayuela",
    "author": "Julio Cortázar",
    "genre": "Novela experimental",
    "year": 1963,
    "stock": 10
  },
  {
    "title": "Ficciones",
    "author": "Jorge Luis Borges",
    "genre": "Cuentos fantásticos",
    "year": 1944,
    "stock": 6
  },
  {
    "title": "La casa de los espíritus",
    "author": "Isabel Allende",
    "genre": "Realismo mágico",
    "year": 1982,
    "stock": 9}])

    3 -  db.books.find({genre: "Realismo mágico"}) Consulta por género
    db.books.find({year: {$gte: 1960, $lte: 1980}}) Consulta por año, siendo
    $gte mayor o igual y $lte menor o igual.

    4 - db.books.updateOne({title: "El Túnel"}, {$set: {stock: 15}})
    db.books.updateOne({title: "Rayuela"}, {$set: {stock: 20}})  Actualizando el stock de 2 libros

    5 - db.books.updateOne({title: "Rayuela"}, {$set: {stock: 20}}) Eliminando libro por título.
