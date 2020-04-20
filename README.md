![banner readme](https://user-images.githubusercontent.com/12829262/79766521-5ff45500-8328-11ea-8084-3849700180c7.png)
# DNSQuery
Dos funciones personalizadas para hojas de cálculo de Google desarrolladas en Apps Script que proporcionan un envoltorio para la función `NSLookup`, tal y como aparece en la [documentación](https://developers.cloudflare.com/1.1.1.1/fun-stuff/dns-in-google-sheets/) del servicio de resolución de nombres de CloudFlare.

En esta [hoja de cálculo](https://docs.google.com/spreadsheets/d/1yq3KJGtQB4OX5y0Qz8FgM7Z88d00rXtP_aKc79Ki1BE/template/preview) se pueden encontrar sendos ejemplos de uso.

# Modo de uso
1. Abre el editor GAS de tu documento (`Herramientas` ⏩ `Editor de secuencias de comandos`), pega el código que encontrarás dentro del archivo `Código.gs` de este repositorio y guarda los cambios. Debes asegurarte de que se esté utilizando el nuevo motor GAS JavaScript V8 (`Ejecutar` ⏩ `Habilitar ... V8`).
2. Hazte una copia de esto :point_right: [DNS Query # demo](https://docs.google.com/spreadsheets/d/1yq3KJGtQB4OX5y0Qz8FgM7Z88d00rXtP_aKc79Ki1BE/template/preview) :point_left: y elimina el contenido.

# Función CONSULTADNS()
Consulta el registro indicado en el o los dominios que se pasan como parámetro utilizando el servicio de resolución de nombres de CloudFlare.

`=CONSULTADNS(registroDNS, lista_dominios)`

Donde:
- `registroDNS`: Alguna de estas cadenas de texto: **A | AAAA | CAA | CNAME | DS | DNSKEY | MX | NS | NSEC | NSEC3 | RRSIG | SOA | TXT**
- `dominios`: Un dominio válido o un intervalo con varios de ellos.

Ejemplo:

`=CONSULTADNS(B12;A3:A12)`

![dnsquery1](https://user-images.githubusercontent.com/12829262/79770552-dcd5fd80-832d-11ea-8859-04b461d2f9da.png)

# Función ESGOOGLEMAIL()
Determina si un email o dominio (o lista de emails o dominios) está gestionado por Google o no.

`=ESGOOGLEEMAIL(lista_emails_o_dominios)`

Donde `lista_emails_o_dominios` es una dirección de correo electrónico o dominio o un intervalo de ellos con varios de ellos.

Ejemplo:

`=ESGOOGLEMAIL(A3:A13)`

![Selección_053](https://user-images.githubusercontent.com/12829262/79771812-98e3f800-832f-11ea-8839-0f9999de9e66.png)

# Licencia
El código original de la función `NSLookup()` pertenece a CloudFlare.

Funciones `CONSULTADNS()` y `ESGOOGLEMAIL()` ©  2020 Pablo Felip Monferrer ([@pfelipm](https://twitter.com/pfelipm)). Se distribuye bajo licencia MIT.
