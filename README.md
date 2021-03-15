# Prueba de DevOps: Hacer un Docker para nginx

Para esta prueba deberás hacer un container Docker para ejecutar el servidor web **nginx** con ciertos requisitos. Usamos dos modulos (plugins) no suministrados por la distribución nginx oficial:

- [Nginx Push Stream](https://github.com/wandenberg/nginx-push-stream-module)
- [Headers More](https://github.com/openresty/headers-more-nginx-module)

Además de estos dos módulos no oficiales, compilamos el nginx sólo con los siguientes módulos activados:

- ipv6 (`--with-ipv6`)
- stream (`--with-stream`)
- http\_stub\_status\_module (`--with-http_stub_status_module`)
- http\_realip\_module (`--with-http_realip_module`)
- http\_ssl\_module (`--with-http_ssl_module`)
- http\_v2\_module (`--with-http_v2_module`)
- http\_gzip\_static\_module (`--with-http_gzip_static_module`)

Además de eliminar de la compilación los siguientes módulos:

- mail\_pop3\_module (`--without-mail_pop3_module`)
- mail\_imap\_module (`--without-mail_imap_module`)
- mail\_smtp\_module (`--without-mail_smtp_module`)

## Requisitos principales:

- Construir una imagen de Docker para **compilar nginx** con los módulos requeridos.
- Suministrar un `Dockerfile` que prepare esta imagen lista para servir un `index.html` del directorio `/var/www/`, que se montará como volumen externo.

## Requisitos alternativos (¡¡Extra puntos!!):

- Utilizar como base una imagen de Docker lo más pequeña posible (alpine, busybox, ...).
- Explicar los problemas, pros y contras, que te has encontrado al hacer la imagen.
 
