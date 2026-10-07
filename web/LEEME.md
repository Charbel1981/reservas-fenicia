# Nueva web de fenicia.es

Rediseño de la portada de fenicia.es. Mantiene toda la carta y el sistema de pedidos de WooCommerce, y añade:

- Portada con propuesta clara, horario ("abierto ahora"), dirección, teléfono y botón de reservar.
- Carta con buscador, filtros (vegano / vegetariano / picante) y erratas corregidas.
- Pedido con selección recoger (−10 %) / domicilio. Al finalizar, los platos se añaden al carrito real de WooCommerce y se abre `/checkout/`.
- Formulario de reserva (sala o terraza) y bloque de grupos.
- Versión en inglés (botón ES / EN).
- Datos estructurados `Restaurant` para Google, mapa que solo se carga si el usuario lo pide (sin cookies de Google por defecto).
- Barra fija inferior en móvil: llamar · reservar · pedido.

## Archivos

- `index.html`: la página.
- `menu.js`: la carta (115 platos). El `id` de cada plato es el ID de producto de WooCommerce. Para cambiar precios o platos, editar aquí.

## Antes de publicar (revisar en `CONFIG`, dentro de `index.html`)

1. **Horario**: está puesto 13:00–00:00 (viernes y sábado hasta 00:30), sacado de directorios. Confirmar. Cambiarlo también en el bloque `application/ld+json`.
2. **Reservas**: rellenar `reservasWhatsapp` (número con 34 delante) o `reservasEmail`. Si se dejan vacíos, el formulario muestra el botón de llamar.
3. **Etiquetas vegano / vegetariano / picante** en `menu.js` (campo `t`): son una propuesta; revisarlas con cocina.
4. **Descuento de recogida**: la web muestra el −10 % orientativo; el descuento real lo sigue aplicando WooCommerce en el checkout.

## Cómo publicarla en fenicia.es

Tiene que servirse desde el propio dominio fenicia.es (las fotos usan las rutas `/wp-content/uploads/...` y el carrito usa `/?wc-ajax=add_to_cart`). Opciones:

- Crear en WordPress una página con una plantilla en blanco y pegar el contenido, o
- Subir `index.html` y `menu.js` a una carpeta (p. ej. `/nueva/`) para probarla en `fenicia.es/nueva/` antes de cambiar la portada.

Fuera de fenicia.es las fotos no cargan (se ve la inicial del plato) y el botón "Finalizar pedido" no puede conectar con la tienda.
