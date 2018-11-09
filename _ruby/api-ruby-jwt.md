---
autor: "Richard Hoyos"
layout: post
title: "Autenticación con Ruby on Rails y JSON Web Tokens"
date: 2018-11-21
categories: [post]
description:  "Como crear una autenticación con Ruby on Rails y JWT."
image: /assets/images/ror/rorandjwt.png
---

En este articulo estare mostrando como crear un API con Ruby on Rails 5 en modo API. Esta API cuenta ademas con autenticación usando JSON Web Token, para esto estaremos usando la gema ```knock``` la cual os permite realizar una configuración sencilla de JWT en Rails.

Este API será un CRUD para administrar una Agenda de Profesores y usando JWT permitiremos hacer estas transacciones solo con el usuario que se encuentre autenticado.

Entonces, ¡Manos a la Obra!.

### Paso 1 - Creando la API en Rails

En este paso debemos tener instalado:

 1. [Ruby on Rails](https://guides.rubyonrails.org/getting_started.html)
 2. [PosgreSQL](https://www.postgresql.org/) (opcional)

```rails new rails-api --api -d postgresql -T```

Si deseas usar SQLite y MiniTest puedes ejecutar:

```rails new rails-api --api```

**MiniTest:** Es un framework para testing. Este provee un conjunto de ```assertions``` que hacen las pruebas mas limpias y leibles.

### Paso 2 - Instalando Gemas

Editemos el archivo ```Gemfile``` donde incluiremos las gemas que necesitamos para la API.

````Ruby

# Rack CORS para manejar fuentes compartidas con Cross-Origin (CORS), permitiendo peticiones AJAX
gem 'rack-cors'

# Usamos knock para autenticar con el JWT
gem 'knock'

# Usamos Active Model Serializers para definir las respuestas del API en JSON
gem 'active_model_serializers', '~> 0.10.0'

````

Instalamos las nuevas gemas

```bundle install```

### Paso 3 - Creando Entidades

En este punto crearemos 2 entidades, la primera es la entidad de usuario la cual usaremos para la autenticación de los usuarios en la API, la segunda es la entidad de profesores la cual nos permitirá administrar los datos de los profesores.

````Bash

# Entidad Usuario
rails g scaffold User name:string last_name:string \
               email:string birthdate:date password_digest:string

# Entidad Profesores
rails g scaffold User name:string last_name:string \
               address:string phone:date cellphone:string

````

Antes de realizar la migración debemos crear la base de datos (solo si usamos PostgreSQL).

```rails db:create```

Y luego la migración

```rails db:migrate```

