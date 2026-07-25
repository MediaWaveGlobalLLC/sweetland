# Sweet Land — sitio de marca

Landing conceptual para **Sweet Land**, candy shop en el Hipódromo Camarero,
Canóvanas, Puerto Rico. Construida sobre el revamp visual de 2026.

Sitio estático: HTML y CSS, sin build ni dependencias.

## Estructura

```
index.html            Página completa
styles.css            Sistema de diseño (tokens + componentes)
assets/logo.png       Logotipo — lettering tipo caramelo
assets/empaques.jpg   Fotografía de empaque
```

## Sistema de diseño

**Color** — cinco valores fijos, definidos como custom properties en `:root`.
Los neutros llevan sesgo morado a propósito; no son grises puros.

| Token      | Hex       | Uso                          |
|------------|-----------|------------------------------|
| `--chicle` | `#FF3D96` | Acento principal, botones    |
| `--mango`  | `#FFC42E` | Realces, etiquetas sobre uva |
| `--pina`   | `#12BFAF` | Secundario, foco de teclado  |
| `--uva`    | `#7A2E9E` | Fondos densos, tinta         |
| `--crema`  | `#FFF4E4` | Fondo base                   |

**Tipografía** — tres roles: display (900, versalitas, tracking negativo),
cuerpo, y una condensada en mayúsculas con tracking abierto para etiquetas.
No se cargan webfonts: el CSP de despliegue bloquea CDNs de fuentes y una
fuente que no carga es peor que una pila de sistema bien elegida.

**Tema** — claro y oscuro. La preferencia del sistema entra por
`prefers-color-scheme`; `data-theme` en el elemento raíz la sobreescribe en
ambas direcciones.

## Ver en local

```bash
python3 -m http.server 4173
```

Luego abrir <http://localhost:4173>.

## Pendiente

Los campos marcados **Por confirmar** en la sección *Visítanos* son
marcadores de posición: días de carrera, horario y teléfono esperan los
datos reales del negocio.

Los assets de marca son generados para propuesta — sirven para presentar la
dirección visual, no como arte final de producción. El logotipo necesita
vectorizarse antes de cualquier uso impreso o de rotulación.
