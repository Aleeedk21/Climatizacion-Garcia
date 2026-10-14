# García Climatización — cambios del 14/10/2026

## Novedades de esta versión
- **Carrito en la tienda:** botón "Agregar al carrito" en cada producto. El icono flotante del carrito no se ve al entrar: aparece recién cuando alguien agrega un producto. El cliente ve su pedido (cantidades y total) y lo envía por WhatsApp. **No cobra nada en la web**: disponibilidad y forma de pago se acuerdan por WhatsApp. El carrito se guarda en el navegador del visitante y se registra el evento `add_to_cart` en GA4.
- **Logo de TechCalc** junto al botón "Probar la calculadora completa" (archivo `img/techcalc-logo.svg`, tomado de tu repo de TechCalc).
- Para cambiar precios o agregar productos: cada tarjeta de la tienda tiene el precio visible y, en el botón "Agregar al carrito", los atributos `data-name` y `data-price`. Tienen que coincidir.

## Cómo publicar
1. En GitHub, repo `Climatizacion-Garcia` → **Add file → Upload files**.
2. Subí, respetando la estructura: `index.html`, `sitemap.xml`, `og-image.jpg` y la carpeta `img/` completa.
3. **No borres nada todavía.** Los archivos originales (fotos y videos pesados) siguen en el repo; el sitio nuevo ya no los usa. Cuando verifiques que todo anda bien, podés borrarlos para aliviar el repo (guardá una copia antes).
4. Esperá 1–2 minutos y abrí https://garciaclimatizacion.com.ar/ (recargá con Ctrl+F5).

## Qué cambió
- **Medición:** evento `whatsapp_click` en GA4 (con el parámetro `link_location`: header, portada, producto-capacitor, producto-kit, cta-final, footer, boton-flotante, calculadora). No se envía número ni mensaje. También `calculadora_frigorias` cuando alguien usa la calculadora.
- **Conversión:** menú de navegación (escritorio), botón "Ver trabajos realizados", acceso a repuestos desde la portada, botón flotante de WhatsApp en móvil (aparece al bajar de la portada) y texto "Pedir presupuesto por WhatsApp".
- **Calculadora de frigorías** nueva en la página (`#calculadora`), con validación, BTU y consulta opcional por WhatsApp.
- Debajo de la calculadora hay un botón "Probar la calculadora completa" que abre TechCalc (techcalcpro.netlify.app) en otra pestaña y registra el evento `techcalc_click`.
- **Rendimiento:** imágenes a WebP (de ~23 MB a ~0,7 MB), videos reducidos (portada de 2,7 MB a 0,65 MB; galería de 9,5 MB a 1,2 MB), `poster`, `width`/`height`, galería de video con `preload="none"`, y el contenido ya no queda oculto si falla el JavaScript.
- **SEO:** title y description más cortos, se quitaron `meta keywords` y metas `geo.*`, se agregó Ciudadela, horarios corregidos (atención lunes a sábado de 8 a 18 h; trabajos con cita previa) y `og-image.jpg` creada.
- **Tienda:** fotos reales del capacitor y del kit. La del kit es una imagen ilustrativa y así está indicado.

## Cómo verificar el evento en GA4
1. GA4 → **Administrar → DebugView**.
2. Abrí el sitio en el celular o en una pestaña con la extensión "Google Analytics Debugger" activada.
3. Tocá un botón de WhatsApp. Tiene que aparecer `whatsapp_click` en DebugView.
4. Pasadas 24 h, mirá **Informes → Interacción → Eventos**.
5. Recién cuando lo veas funcionando, en **Administrar → Eventos** marcá `whatsapp_click` como evento clave.

## Search Console (lo hacés vos)
1. https://search.google.com/search-console → **Añadir propiedad → Dominio** → `garciaclimatizacion.com.ar`.
2. Google te da un registro TXT: cargalo en el DNS de tu proveedor de dominio y pulsá Verificar (puede tardar).
3. **Sitemaps** → agregá `sitemap.xml`.
4. **Inspección de URL** → pegá la home y pedí indexación.
5. Después de unos días: **Rendimiento** (clics, impresiones, consultas, posición) y **Páginas** (indexación).

## Pendientes
- Medir con PageSpeed Insights (https://pagespeed.web.dev) en móvil y escritorio, antes y después.
- Comprobar que `www.garciaclimatizacion.com.ar` redirija al dominio sin `www`.
- Foto real del kit y una del capacitor de mejor resolución (la actual es chica).
- Testimonios y más trabajos reales con barrio, cuando los tengas.
- Cargar el Perfil de Empresa de Google si todavía no lo tenés.
