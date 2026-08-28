# marlonpya.github.io

Portafolio personal de **Marlon Mauro Arteaga Morales** — Lead Mobile Android &amp; iOS.

**En vivo:** https://marlonpya.github.io

---

## Qué es

Un solo `index.html`. Sin build, sin dependencias, sin framework. Se despliega tal cual
y el catálogo de repositorios se lee de la API pública de GitHub en el navegador de
quien visita, así que no se queda desactualizado.

### Decisiones de diseño

- **El color codifica plataforma, no decora.** Morado Kotlin (`#6E3AF2`) para Android,
  naranja Swift (`#DE4225`) para iOS, degradado de ambos para Kotlin Multiplatform.
  Se aplica igual en el stack, en las apps y en el lenguaje de cada repositorio.
- **Tema claro por defecto**, con conmutador a oscuro. Respeta `prefers-color-scheme`
  y recuerda la elección en `localStorage`.
- **Tipografías:** Instrument Sans (títulos y texto) e IBM Plex Mono (rótulos, datos, código).
- La portada declara el perfil como un bloque de configuración Kotlin — resaltado con
  HTML semántico, no una imagen.
- Responsive, foco de teclado visible, respeta `prefers-reduced-motion`.

---

## Estructura

```
.
├── index.html    # el sitio completo: markup, estilos y lógica
├── cv.pdf        # CV descargable (enlazado desde la sección Contacto)
└── README.md
```

## Configurar

Todo lo editable está en un solo bloque, al final de `index.html` dentro de `<script>`,
bajo el comentario `CONFIGURACIÓN`:

| Constante | Para qué sirve |
|---|---|
| `USUARIO_GITHUB` | Usuario cuyos repos se consultan. |
| `REPOS_DESTACADOS` | Repos a mostrar, en ese orden. Vacío = selección automática por relevancia. |
| `NOTAS_REPOS` | Descripción propia para repos que en GitHub no tienen `description`. |
| `CONTACTO` | Correo, LinkedIn, GitHub y ruta del CV. |
| `APPS` | Proyectos propios. `plataforma` acepta `android`, `ios` o `kmp`. |
| `TRAYECTORIA` | Experiencia profesional. |

Nada de esto requiere recompilar: se edita, se guarda y se sube.

## Desplegar

Al llamarse el repositorio `marlonpya.github.io`, GitHub Pages se activa solo al hacer
push a `main`. No hay que tocar Settings.

```bash
git add index.html cv.pdf README.md
git commit -m "Actualiza portafolio"
git push
```

El sitio queda publicado en un par de minutos.

## Notas

- La API de GitHub sin autenticar permite 60 consultas por hora y por IP. Cada visita
  gasta una; si alguien recarga muchas veces verá el aviso de límite alcanzado.
- Si cambias tus repos fijados en GitHub, actualiza `REPOS_DESTACADOS` para que coincida.

---

Hecho en Lima, Perú.
