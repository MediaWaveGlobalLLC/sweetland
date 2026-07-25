# SweetLand — sitio del kiosco

Sitio del kiosco **SweetLand**, dentro del Hipódromo Camarero en Canóvanas,
Puerto Rico. Muestra el menú real con precios y cómo llegar.

Estático: HTML, CSS y un script de doce líneas. Sin build, sin dependencias.

## Estructura

```
index.html               Página completa
styles.css               Sistema de diseño (tokens + componentes)
assets/logo.png          Logotipo propuesto (lettering tipo caramelo)
assets/comida.jpg        Bodegón de producto para la portada
assets/kiosco-*.jpg      Fotos reales del kiosco, para ubicarse
assets/fonts/*.woff2     Bricolage Grotesque y Geist, auto-alojadas
```

## Diseño

**Color.** Los tres colores salen de los rótulos del propio kiosco, no de
una paleta inventada: magenta (`#E01B6A`), azul cielo (`#4FC3E8`) y amarillo
mango (`#FFC42E`), sobre tinta morada (`#24103A`). Se extrajeron por
cuantización de matiz de las fotos del local.

**Tipografía.** Bricolage Grotesque para display y Geist para texto, ambas
auto-alojadas en `assets/fonts/` con `font-display: swap`. Sin CDN de
fuentes.

**Iconos.** Phosphor, obtenidos con `better-icons`. Solo se usan donde el
icono es exacto (WhatsApp, pin de mapa, reloj). No hay iconos por renglón
del menú porque Phosphor no tiene algodón de azúcar, frappé ni fresa con
crema, y forzar un `hamburger` para el hot dog es peor que no poner nada.

**Movimiento.** Entrada escalonada en la portada, revelado de tarjetas por
`IntersectionObserver`, cinta corrediza y rayos de feria en rotación lenta.
Todo se apaga con `prefers-reduced-motion`.

## El menú

Los trece renglones y sus precios están transcritos de la foto del menú
impreso del kiosco. Todos los precios van **antes de IVU**.

### Pendiente de confirmar con el negocio

Tres cosas quedaron sin verificar y están marcadas con comentarios en
`index.html`:

1. **Piragua** y **café** traen dos precios cada uno en el menú impreso, sin
   decir a qué tamaño corresponde cada cual. La página lista los dos sin
   asumir.
2. Los añadidos de nachos (bacón, queso extra) están impresos con signo de
   **euro** (`.93€`). Se asumió `$0.93`.
3. El precio de la **piña colada** estaba parcialmente tapado por un reflejo
   en la foto. Se leyó como `$6.00`.

También falta el **horario**, que aparece marcado como tal en la sección
*Dónde estamos*.

### Sobre el nombre

Hay tres grafías en circulación: el rótulo del kiosco dice **SweetLand**, el
menú impreso dice **SWEELAND** y el logotipo propuesto dice **SWEET LAND**.
El sitio usa `SweetLand`, que es lo que dice la rotulación. Si se quiere
unificar, el logotipo hay que re-letrarlo.

## Ver en local

```bash
python3 -m http.server 4173
```

## Notas

El logotipo es un **PNG generado** para la propuesta de revamp. Antes de
usarlo en rotulación o impresión hay que vectorizarlo.

El bodegón de producto (`comida.jpg`) también es generado. Muestra los
productos reales del menú, pero no es una foto del kiosco: conviene
sustituirlo por fotografía real cuando la haya.

Las fotos del kiosco son reales y muestran clientes de espaldas, sin caras
identificables.
