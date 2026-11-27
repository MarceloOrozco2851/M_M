# Marcelo & Melida · Nuestra historia

Página de regalo con la estética de la referencia (azul noche + dorado): portada con sobre, nombres, fotos con marco blanco, contadores en vivo (incluido el tiempo desde la última vez que se vieron), mensaje privado con **carta escrita a mano**, línea del tiempo real, mapa de la distancia, galería, lista, vales y ruleta.

## Cómo verla

Abre `index.html` con doble clic. Funciona sin servidor; las fotos están en `fotos/`, la canción en `audio/` y solo las tipografías se descargan de Google Fonts.

## Estructura

1. **Portada:** “UN REGALO PARA TI” → nombre → sobre con sello → “Toca para abrir”.
2. **Sitio (scroll):**
   - Nombres + “Guatemala · Honduras”.
   - Foto de su cumpleaños en Metro Mall.
   - **Tiempo de conocernos (primer saludo):** fecha 27/11/2024 · 22:13, contador y reloj en vivo.
   - **Tiempo de estar juntos (la pregunta):** fecha 14/07/2026, contador, reloj en vivo y total de días juntos.
   - **Tiempo sin verte (la última vez que nos vimos):** fecha 5/9/2026, contador, reloj en vivo y total de días sin verse.
   - “Mensaje privado → Abrir carta”: la carta escrita, la firma y **la carta a mano del PDF** (se puede ampliar).
   - Foto del primer encuentro (Centro Cívico).
   - “Lo que más amo de ti”.
   - **Línea del tiempo:** 27/11/2024 22:13 → 14/07/2026 → 4/9/2026 12:00 → 5/9/2026 12:30 → 7/9/2026 5:30 → hoy.
   - **Nuestra distancia:** mapa Guatemala ↔ Honduras con un bus que se mueve por la ruta y las 14 fotos pequeñas del viaje repartidas alrededor del arco.
   - **Nuestros lugares:** mapa satelital interactivo (Leaflet + Esri) con un pin por lugar; al tocar un pin (o una parada) se abre el álbum de fotos de ese lugar.
   - Foto de Metro Mall.
   - **Galería:** las fotos de los días 4 y 5 de septiembre de 2026.
   - “Nuestra lista” (checklist interactiva).
   - “Nuestros vales de amor” (se pueden canjear).
   - Ruleta de citas (7 opciones: Cena · Cine · Helado · Foto · Llamada · Videollamada · Sorpresa).
   - **Sobre los atardeceres:** enlace a la página de los siete atardeceres para la graduación.
   - Cierre + firma + dedicatoria final de Eberth (Gaby).

## Personalizar

Todo el contenido está en el bloque de constantes al inicio del `<script>` de `index.html`:

```js
const ELLA = 'Melida';
const EL   = 'Marcelo';
const FECHA_INICIO  = '2024-11-27T22:13:00';  // primer saludo (contador principal)
const FECHA_RELACION = '2026-07-14';          // inicio de la relación (línea de abajo)
const FECHA_ULTIMA_VEZ = '2026-09-05T00:00:00'; // última vez que se vieron (tiempo sin verte)

const GUSTOS = [ ... ];
const MOMENTOS = [ { fecha, titulo, texto }, ... ];
const LUGARES = [ { nombre, detalle }, ... ];
const LISTA = [ ... ];
const VALES = [ ... ];
const RULETA = [ ... ];
```

## Fotos

Están en `fotos/` ya optimizadas (JPEG). Para cambiar una, reemplaza el archivo o edita el `src` en el HTML.

| Archivo | Contenido |
|---|---|
| `carta-mano.jpg` | Carta escrita a mano (desde el PDF `MELIDA.pdf`) |
| `centro-civico-1.jpg` | Plaza del Centro Cívico |
| `centro-civico-2.jpg` | Vista de la plaza desde arriba |
| `centro-civico-3.jpg` | Bebidas y McDonald's (primer encuentro) |
| `centro-civico-4.jpg` | Pérgola y flores |
| `centro-civico-5.jpg` | Torre Chortí |
| `centro-civico-6.jpg` | Pasillo del Centro Cívico |
| `metro-mall-1.jpg` | Cumpleaños de Melida (velas) |
| `metro-mall-2.jpg` | Caminando por Metro Mall |
| `metro-mall-3.jpg` | Comida en Metro Mall |
| `graduacion-melida.jpg` | Retrato de graduación de Melida (polaroid flotante) |

### Fotos del viaje

Están en `fotos/viaje/`, optimizadas a 480 px y sin metadatos. Se muestran como miniaturas tipo polaroid dentro del mapa de **“Nuestra distancia”**, repartidas alrededor de la ruta del bus (son decorativas, no se amplían):

| Archivo | Contenido |
|---|---|
| `viaje-sello-guatemala.jpg` | Sello de migración de Guatemala |
| `viaje-tienda-merida.jpg` | Tienda de bicicletas Mérida |
| `viaje-policia.jpg` | Policía Nacional Civil desde la ventana |
| `viaje-aduana-el-amatillo.jpg` | Aduana Terrestre El Amatillo |
| `viaje-bus-noche.jpg` | Asiento del bus de noche |
| `viaje-habitacion.jpg` | Habitación del hotel con la maleta |
| `viaje-bus-pantalla.jpg` | Pantalla y pasillo del bus |
| `viaje-bus-puerta-noche.jpg` | Puerta del bus abierta de noche |
| `viaje-bus-pasillo.jpg` | Pasillo con asientos azules |
| `viaje-bus-marcopolo.jpg` | Bus Marcopolo con las maletas |
| `viaje-k9.jpg` | Perro K9 en la puerta del bus |
| `viaje-ventana-lluvia.jpg` | Ventana con gotas de lluvia |
| `viaje-calle-noche.jpg` | Calle de noche con el termo azul |
| `viaje-frontera-el-salvador.jpg` | Letrero de El Salvador en la frontera |

**Carta a mano:** viene de `MELIDA.pdf` (1 página escaneada). Se recortó, se convirtió a JPEG y se agregó al modal de “Abrir carta”, debajo del texto. Al tocarla se abre en un visor a pantalla completa y se puede acercar tocando la imagen.

**Nota de privacidad:** el boleto de bus no se publicó porque muestra el número de pasaporte y el código QR. El regreso se cuenta en texto, sin publicar el documento.

## Audio

- **Canción de fondo:** «Toma Mi Mano» de Tercer Cielo, en `audio/toma-mi-mano.mp3` (128 kbps, en loop).
- Arranca sola al pulsar **“Toca para abrir”** (ese clic permite el autoplay) y se puede pausar o retomar con el botón flotante de la nota musical.
- La página solo usa la copia optimizada; el archivo original `Tercer Cielo - Toma Mi Mano.mp3` no se referencia (podés quitarlo de la copia que publiques).

## Publicar y compartir

1. **Netlify Drop** — https://app.netlify.com/drop (arrastra la carpeta completa, con `fotos/` y `audio/`).
2. **GitHub Pages** — Settings → Pages → rama `main` / root.
3. **Vercel** — `npx vercel` dentro de la carpeta.

## Mapa de lugares

La sección **“Nuestros lugares”** usa Leaflet con imágenes satelitales de Esri (sin API key) y un pin dorado por parada.

- Las coordenadas están en `PARADAS`: `lat` y `lng` de cada lugar.
- Al tocar un pin o una tarjeta se abre el álbum de fotos de esa parada.
- El enlace **“Abrir en Google Maps”** lleva al lugar activo en Google Maps.
- Si el mapa no carga (sin internet), aparece un enlace directo a Google Maps.

## Detalles técnicos

- Sin frameworks ni build: un solo `index.html` + `fotos/` y `audio/`.
- Música de fondo con `<audio>` («Toma Mi Mano») y botón flotante para pausar/retomar.
- Contador principal (desde el primer saludo) + línea con los días de relación.
- Interacciones: modal de carta con foco atrapado, visor de la carta a mano con zoom, checklist, vales canjeables, ruleta con resultado consistente con la aguja.
- Responsive probado en 360 px, 412 px y escritorio; respeta `prefers-reduced-motion`.

## Efectos de tulipanes

- **Jardín:** 40 tulipanes en la portada y 32 al cierre, en dos filas (los de atrás más pequeños y tenues), meciéndose con el viento. Al tocar uno, se sacude y se le caen las hojas.
- **Pétalos cayendo:** capa de pétalos dorados, crema y rosa en toda la página.
- **Lluvia al abrir:** al pulsar “Toca para abrir” salen 32 pétalos desde el sobre.
- **Fotos flotantes:** cinco polaroids pequeñas que se balancean alrededor de la página.
- **Detalles:** tulipán en el divisor de los nombres, en el pie y como icono de la pestaña.
- Todo se oculta automáticamente si el dispositivo pide movimiento reducido.
