# Plantilla web para despacho de abogados

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css&logoColor=white)
![Sin JavaScript](https://img.shields.io/badge/JavaScript-ninguno-lightgrey)
![Sin dependencias](https://img.shields.io/badge/dependencias-0-brightgreen)
![Sin cookies](https://img.shields.io/badge/cookies-ninguna-brightgreen)

Web estática de una página, más una página de textos legales, pensada para un despacho de abogados. No contiene datos de ningún cliente: todo el contenido es de ejemplo y hay que sustituirlo antes de publicar.

## Características

- **HTML y CSS, nada más.** Sin build, sin dependencias y sin JavaScript.
- **Sin peticiones a terceros.** Las fuentes (Archivo y Newsreader) están autoalojadas en `fonts/`, así que no se llama a Google Fonts. El sitio no usa cookies ni trata datos personales, y la política de privacidad lo da por hecho.
- **Sin formulario de contacto.** El contacto es por teléfono y correo.
- **Adaptable a móvil** con CSS Grid, Flexbox y `clamp()`.
- Datos estructurados (JSON-LD), Open Graph y `canonical` ya preparados.

## Estructura

| Fichero | Contenido |
|---|---|
| `index.html` | Página principal: cabecera, hero, banda de credibilidad, áreas de práctica, trayectoria, método, contacto y pie. |
| `legal.html` | Aviso legal (`#aviso-legal`) y política de privacidad (`#privacidad`). |
| `estilos.css` | Hoja de estilos única para las dos páginas. |
| `fonts/`, `img/`, `favicon.svg` | Recursos estáticos. |
| `robots.txt` | Bloquea la indexación mientras la web está en pruebas. |
| `PERSONALIZAR.md` | Lista de datos que hay que sustituir para cada cliente. |

## Verlo en local

Todas las rutas son relativas; basta con un servidor estático en la raíz:

```
python3 -m http.server 8000
```

y abrir `http://localhost:8000/`.

## Personalizar

Los datos de ejemplo («Nombre Apellido», «Ciudad», `tudespacho.es`, `900 00 00 00`, `info@tudespacho.es`, número de colegiado, cifras, trayectoria…) están marcados en el HTML con comentarios `DATO PENDIENTE`. En `legal.html` los huecos aparecen resaltados en amarillo.

La lista completa está en [PERSONALIZAR.md](PERSONALIZAR.md). Ojo con el teléfono: aparece en varios sitios de las dos páginas y en el JSON-LD.

## Publicar

La plantilla **bloquea la indexación** a propósito. Al publicar en el dominio definitivo:

1. Sustituir `robots.txt` según las instrucciones de sus comentarios.
2. Quitar `<meta name="robots" content="noindex, nofollow">` de `index.html` y `legal.html`.

Las fotografías de `img/` son de Unsplash (uso comercial permitido).
