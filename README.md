# Acceder a MongoDB desde una aplicación Node.js contenida en un contenedor Docker

Este ejemplo ejecuta una aplicación de ejemplo realizada en Node.js que se conecta a una base de datos MongoDB que se ejecuta en la máquina local (host).

Para hacer uso de éste ejemplo clona este repositorioi en tu máquina local y luego ejecuta el script de docker-compose

## Observación:
Si se tiene el un cortafuego activo, se debe dar acceso al puerto 27017 de MongoDB, ya que el acceso desde el contenedor será considerado un acceso remoto

## Uso:

* Clona éste repositorio
* Reemplazar en la sección extra_hosts **docker-composer.yml** establecer la dirección IP de tu **Host**
* Genera el contenedor y ejecuta la aplicación

``` bash
$ docker-compose up -d
```

* Luego, desde postman puedes probar la API, por ejemplo con la siguiente secuencia:

### Registra un producto

**Endpoint:** localhost:3000/api/product
**Método:** POST
**Datos:** en formato JSON
``` json
{
    "price": 1090,
    "_id": "5babfc4551574d5bb55da969",
    "name": "MacBook Pro",
    "category": "computers",
    "description": "El portátil ultraligero de Apple en 13 pulgadas",
    "__v": 0,
    "picture": "mackboo_air.png"
}
```

### Consultar los productos registrados
**Endpoint:** localhost:3000/api/product
**Método:** GET
