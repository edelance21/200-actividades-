# Guía de lanzamiento · Mamá, estoy aburrido

Acompaña a la página de venta (`index.html`) y a las imágenes de anuncio.

---

## 1. Qué es el "Pack completo"

**Pack completo = kit principal (7 archivos, 200 actividades) + 50 dibujos para colorear + 6 juegos de mesa.**

| Producto | Precio por separado |
|---|---|
| Kit principal (200 actividades + guía + 5 bonos) | US$12.97 |
| 50 dibujos para colorear | US$7.97 |
| 6 juegos de mesa | US$9.97 |
| **Suma por separado** | **US$30.91** |

### Precio del pack (decide tú; el ahorro se calcula solo)
| Precio del pack | Ahorro real frente a comprar por separado |
|---|---|
| US$19.97 | 35% |
| **US$22.97 (el que dejé)** | **26%** |
| US$24.97 | 19% |
| US$27.97 (precio regular fuera de campaña) | 10% |

Si quieres que el pack cueste más **y** que el ahorro se vea más grande, la única forma honesta es subir de verdad los precios por separado (por ejemplo, kit a US$17.97). El porcentaje siempre debe salir de precios que de verdad cobras.

---

## 2. Ofertas y cuenta regresiva (cómo funcionan)

- Las ofertas se definen como **campañas con fecha de inicio y de fin**, iguales para todos los visitantes (bloque `CONFIG.campaigns` en `index.html`).
- **Durante una campaña:** la barra superior cuenta hacia el final y el pack está a US$22.97.
- **Entre campañas:** la barra cuenta hacia el inicio de la próxima oferta y el pack está a su precio regular (US$27.97). Si no quieres mostrar eso, pon `showNextCampaign: false`.
- **Campañas ya cargadas:** Lanzamiento (**3 oct 2026 al 6 ene 2027**), San Valentín (10–14 feb), Carnaval (24 feb–2 mar), Semana Santa (24–28 mar), Día de las Madres (3–10 may), vacaciones de verano (14–21 jun), regreso a clases (16–23 ago), aniversario (13–20 sep), Halloween (25–31 oct 2027), Black Friday (22–29 nov 2027) y Navidad (13–24 dic 2027). **Son fechas de ejemplo: cámbialas por las que de verdad vas a cumplir.**
- **Importante con una oferta de lanzamiento larga:** el 7 de enero de 2027 el pack debe pasar de verdad a US$27.97 en Hotmart. Si sigue a US$22.97, la página y los anuncios dejarían de ser ciertos.
- Para tener una cuenta regresiva casi siempre visible, programa campañas reales con anticipación (cada semana o cada quincena, con un motivo: Día de las Madres, regreso a clases, vacaciones, aniversario de la tienda...). Cada campaña debe terminar de verdad y el precio debe subir de verdad.
- Si pasa el último día de tu calendario, la barra se oculta sola. Agrega más campañas antes de que eso ocurra.

**Lo que no hace la página (a propósito):** un contador que se reinicia, que es distinto para cada visitante o que "se acaba" sin que cambie nada. Eso convierte la oferta en una afirmación falsa.

---

## 3. Qué editar en `index.html` (bloque `CONFIG`)

1. `links`: 5 enlaces de checkout de Hotmart: `kit`, `dibujos`, `juegos`, `packOferta` (US$22.97) y `packRegular` (US$27.97). Crea el pack con dos ofertas o dos productos, según lo que permita tu cuenta de Hotmart.
2. `prices`: si cambias algún precio, el % se recalcula solo (las imágenes de anuncio no: pídelas de nuevo).
3. `campaigns`: tus fechas reales.
4. `guaranteeDays`: igual a la garantía que elijas en Hotmart (7, 15, 21 o 30 días; en Europa, mínimo 15).
5. `contactEmail`, `termsUrl`, `privacyUrl`.
6. `testimonials`: solo opiniones reales (ver sección 5).

---

## 4. Hotmart · checklist

- [ ] Crear los productos: Kit (US$12.97), 50 dibujos (US$7.97), 6 juegos (US$9.97) y Pack completo con sus dos precios.
- [ ] Garantía: la misma que pusiste en `guaranteeDays`.
- [ ] Subir los 9 PDF (7 del kit + 2 adicionales). Pack completo = los 9.
- [ ] Hacer una **compra de prueba** y revisar el correo de entrega.
- [ ] Pegar los enlaces en `CONFIG.links`.
- [ ] Cada día de cambio de campaña: comprobar que el precio en Hotmart coincide con el de la página.

*Los plazos de garantía de Hotmart (7, 15, 21 o 30 días; mínimo de 15 en Europa) y el hecho de que "el producto no es lo que se prometía en la página" es un motivo de reembolso aceptado salen de su Central de Ayuda y de su guía de reembolsos. Revísalo en tu cuenta antes de publicar.*

---

## 5. Testimonios: cómo tenerlos pronto y que sean reales

**Lo que no se puede hacer:** escribir testimonios de madres que no existen o que no han usado el kit. Para quien compra, "una madre real usó esto y le fue bien" es una afirmación falsa, aunque el producto sea bueno.

**Lo que sí hay en la página ahora mismo:** una sección **"Momentos en los que este kit te salva el día"** con 6 situaciones de ejemplo (tarde de lluvia, viaje en auto, sala de espera, hermanos, antes de dormir, domingo en casa), cada una con el número de actividad. Está rotulada como ejemplos, no como opiniones.

**Cómo conseguir opiniones reales en 5 a 10 días:**

1. Elige 10 madres o padres que no sean tu familia directa.
2. Envíales este mensaje:

> Hola [nombre]. Terminé un kit de 200 actividades imprimibles para niños de 3 a 10 años, sin pantallas. Quiero regalártelo para que lo pruebes con tus hijos una semana. A cambio solo te pido una opinión **sincera** (si algo no te gustó, cuéntamelo también). ¿Me pasas tu correo y la edad de tus hijos?

3. A los 5–7 días pregúntales: ¿qué actividades probaron?, ¿cuáles les gustaron más?, ¿qué cambiarían?, ¿lo recomendarían?, ¿autorizan publicar su respuesta con su nombre y la edad de su hijo/a?
4. Guarda su "sí, autorizo" por escrito.
5. Pega el texto **tal cual** en `CONFIG.testimonials`. Si recibieron el kit gratis, pon `gift: true` y la página mostrará el aviso correspondiente.

```js
testimonials: [
  { text: "Texto exacto que escribió la persona.", name: "Nombre A.", detail: "mamá de un niño de 6 años", gift: true }
]
```

Cuando tengas 3 o más, la sección "Lo que cuentan las familias" aparece sola en la página. Si quieres, también puedo convertirlas en imágenes para anuncios.

---

## 6. Textos para anuncios

> Antes de pagar anuncios, revisa las políticas vigentes de Meta, Google y TikTok sobre anuncios para padres y sobre afirmaciones de ahorro. No pude comprobarlas.
> Evita frases que den a entender que sabes algo personal de quien ve el anuncio.

### Anuncio A · La pregunta (`anuncio_A_pregunta_*`)
**Texto principal:**
¿Otra vez "mamá, estoy aburrido"? 😅
Ten la respuesta lista: 200 actividades imprimibles para que tus hijos jueguen, creen y exploren, sin pantallas.
✔ Casi todo con papel, lápiz y cosas de casa
✔ Para niños de 3 a 10 años
✔ Pago único, descarga inmediata
**Título:** El Kit Anti-Aburrimiento Sin Pantallas · **Botón:** Más información

### Anuncio B · La oferta (`anuncio_B_oferta_pack_*`)
**Texto principal:**
Oferta de lanzamiento hasta el 6 de enero 🎁
Pack completo por US$22.97 en vez de US$30.91 si compras los tres por separado:
• Kit de 200 actividades (con guía y 5 bonos)
• 50 dibujos para colorear
• 6 juegos de mesa para imprimir
Archivos digitales · Pago único · Garantía de 7 días.
**Título:** Pack completo −26% · **Botón:** Comprar ahora

*Las imágenes del anuncio B llevan dentro el precio, el −26% y la fecha. Si cambias algo de eso, pídemelas de nuevo.*

---

## 7. Antes de pagar anuncios

- [ ] Imprimir una muestra de cada producto.
- [ ] Probar 10 actividades con 3 a 5 familias.
- [ ] Compra de prueba en Hotmart: ¿llegan el correo y los 9 PDF?
- [ ] Probar la página en celular (iPhone y Android).
- [ ] Revisar con alguien que conozca la ley de tu país los avisos de seguridad y el texto "no es terapia".
- [ ] Tener listos el correo de contacto, los términos de compra y la política de privacidad.
- [ ] Empezar con poco presupuesto (US$5–10 al día durante 5–7 días) y medir antes de subir.
