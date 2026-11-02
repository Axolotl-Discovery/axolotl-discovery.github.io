# Sitio web — Axolotl Discovery


## Axolotl for Education

Las herramientas educativas se leen de `assets/educacion.json`. Mientras esté vacío (`[]`),
la sección muestra un aviso de "próximamente". Para agregar una herramienta, añade un objeto:

```json
[
  {
    "titulo": "Nombre de la herramienta",
    "nivel": "Bachillerato · Licenciatura",
    "descripcion": "Qué hace y qué aprende el estudiante con ella.",
    "etiquetas": ["Docking", "Interactivo"],
    "enlace": "https://enlace-a-la-herramienta",
    "codigo": "https://github.com/Axolotl-Discovery/repo",
    "imagen": "./assets/educacion/captura.png"
  }
]
```

Solo `titulo` y `descripcion` son obligatorios; los demás campos se pueden omitir.

Para una app que se descarga (en vez de abrirse en el navegador) agrega:
`"descarga": true` (el enlace se abre en la misma pestaña), `"boton": "Descargar para Windows"`
(texto del botón; por defecto "Abrir herramienta") y `"nota": "Windows 10/11 · 160 MB"` (texto pequeño bajo el botón).
Para una app con varias descargas (una por sistema) usa en su lugar `"descargas"`: una lista de
`{"so": "windows" | "mac" | ..., "boton": "Descargar para Mac", "enlace": "..."}`. El botón del sistema del visitante
sale relleno y los demás con borde; con `"secundario": true` la opción sale como enlace pequeño (p. ej. Mac con Intel).
Para que el enlace siempre baje la última versión usa
`https://github.com/<org>/<repo>/releases/latest/download/<archivo>`.

## Conferencias

La sección muestra un carrusel de fotos que se lee de `assets/conferencias.json`. Mientras esté vacío (`[]`),
aparece el aviso "Pronto compartiremos aquí fotos de nuestras conferencias". Sube las fotos a
`assets/conferencias/` y añade un objeto por foto, en el orden en que quieres que salgan:

```json
[
  {
    "imagen": "./assets/conferencias/charla-2027-03.jpg",
    "titulo": "Nombre de la conferencia",
    "descripcion": "Dónde y cuándo, o una frase sobre la foto.",
    "alt": "Descripción de la foto para lectores de pantalla"
  }
]
```

Solo `imagen` es obligatorio; `titulo`, `descripcion` y `alt` son opcionales. Las imágenes deben estar dentro del
propio sitio (la política de seguridad `_headers` solo permite imágenes locales). Conviene reducirlas a unos
1600 px de ancho y menos de 500 KB cada una. La foto se recorta para llenar el marco (16:10 en escritorio,
4:3 en celular), así que deja a las personas hacia el centro.
