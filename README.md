# huanel.github.io

Sitio de las apps. Hoy sirve las políticas de privacidad que App Store Connect
pide por aplicación.

## Cómo sumar una app

Un archivo nuevo en `privacy/`:

```markdown
---
app: NombreDeLaApp
permalink: /privacy/nombredelaapp/
updated: 1 de enero de 2027
repo: https://github.com/Huanel/NombreDeLaApp/issues
---

<p>Qué es la app, en una o dos oraciones.</p>

<h2>Datos que guarda la aplicación</h2>
...
```

Y su entrada en la lista de `privacy/index.md`.

El archivo solo describe **lo propio de esa app**. Todo lo que vale para todas
—qué no se recopila, servicios de terceros, retención, menores, cambios,
contacto— lo agrega `_layouts/privacy.html` al final de la página.

Si algo común deja de ser cierto para una app en particular, la excepción va en
la página de esa app; el layout no se toca. Para retención hay un campo
`retention_note` que agrega un párrafo extra al bloque común.

## Por qué una URL por app y no una sola compartida

Las apps manejan datos distintos: StitchCounter no toca la red, MangaReader lee
archivos que elegís, JellyTV manda credenciales a un servidor que vos indicás.
Una página única obligaría a que la política del contador de tejido hablara de
tokens y servidores, y bastaría con que una app cambiara para dejar el texto
mal para todas.

## Indexación

`robots.txt` pide a los buscadores que no indexen el sitio. Las páginas siguen
siendo **públicas y sin registro**: App Store Connect muestra el enlace de la
política en la ficha de cada app y cualquiera tiene que poder abrirlo.

## Publicación

GitHub Pages sirve este repositorio en `https://huanel.github.io` desde la rama
`main`. No hay nada que compilar a mano.
