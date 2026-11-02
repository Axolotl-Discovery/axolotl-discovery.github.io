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

Las conferencias se leen de `assets/conferencias.json`. Mientras esté vacío (`[]`), la sección muestra
"Próximamente anunciaremos nuestra próxima conferencia". Para anunciar una, añade un objeto:

```json
[
  {
    "titulo": "Título de la conferencia",
    "fecha": "15 de marzo de 2027",
    "hora": "17:00 h (CDMX)",
    "lugar": "Lugar o plataforma en línea",
    "ponentes": "Nombre de quien la imparte",
    "descripcion": "De qué trata y a quién va dirigida.",
    "enlace": "https://enlace-de-registro",
    "boton": "Registrarme"
  }
]
```

Solo `titulo` es obligatorio; los demás campos se pueden omitir. Una vez realizada, quita el objeto
o muévelo a otra lista cuando exista la sección de conferencias pasadas.
