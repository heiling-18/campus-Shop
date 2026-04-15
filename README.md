# eso eso  Campus Shop

**Campus Shop** es una tienda en línea orientada a estudiantes universitarios, donde pueden encontrar productos de estudio, tecnología, confort, comida, higiene y ropa. El proyecto fue desarrollado como una aplicación web estática con HTML y CSS, organizada en múltiples vistas que simulan el flujo completo de compra.

---

##  Estructura del proyecto

```
campus-shop/
│
├── index.html          # Página de inicio (Home)
├── iniciosesion.html   # Login de usuario
├── catalogo.html       # Catálogo de productos
├── carrito.html        # Carrito de compras
├── checkout.html       # Proceso de pago
├── historial.html      # Historial de pedidos
├── perfil.html         # Perfil del usuario
├── vacio.html          # Vista de carrito vacío
│
├── css/                # Estilos por vista
│   ├── home.css
│   ├── iniciosesion.css
│   ├── catalogo.css
│   ├── carrito.css
│   ├── checkout.css
│   ├── historial.css
│   ├── perfil.css
│   └── vacio.css
│
└── img/                # Imágenes de productos y logo
```

---

##  Flujo de navegación

```
iniciosesion.html
      │
      ▼
  index.html  ──────────────────────────────────────┐
      │                                              │
      ├──▶ catalogo.html ──▶ [detalle producto]     │
      │                            │                 │
      │                            ▼                 │
      ├──▶ carrito.html ──▶ checkout.html            │
      │         │                                    │
      │    vacio.html                                │
      │                                              │
      ├──▶ historial.html                            │
      └──▶ perfil.html ◀─────────────────────────────┘
```

---

## 📱 Vistas y Mockups

A continuación se documenta cada pantalla del proyecto junto con su diseño original en mockup (boceto a mano).

---

### 1. 🏠 Inicio — `index.html`

La página principal muestra:
- **Header** con hamburger menu, logo de Campus Shop, botón de inicio de sesión y carrito.
- **Barra lateral (sidebar)** con navegación: Inicio, Mi cuenta, Catálogo, Pedidos.
- **Buscador** de productos.
- **Categorías** en scroll horizontal: Estudio y productividad, Tecnología y accesorios, Confort, Comida, Higiene, Ropa, entre otras.
- **Sección de productos destacados** con scroll horizontal mostrando artículos populares (resaltadores, libro de hábitos, cuaderno, etc.).
- **Sección "Los más populares en Tecnología"** con productos como portátiles, audífonos, cargadores y vidrios templados.
- **Footer** con secciones: Conócenos, Gana Dinero, Pagos, Ayuda.

#### 📝 Mockup — Inicio

> El boceto muestra el layout general: header con hamburger, logo y carrito/login, barra de búsqueda, fila de categorías con íconos (Estudio, Tecnología, Confort, Comida), grid de productos con nombre y precio, y carrusel de tecnología al fondo.

![Mockup Inicio](mockup_inicio.png)

---

### 2. 🔐 Inicio de Sesión — `iniciosesion.html`

Vista de autenticación con:
- Campo de **correo electrónico**.
- Campo de **contraseña**.
- Botón **"Entrar"** que redirige a `index.html`.
- Enlace para **registrarse** (sin implementar aún).

> No tiene sidebar ni header; es una vista centrada y limpia.

---

### 3. 📋 Menú lateral — Sidebar

Presente en casi todas las vistas. Contiene:

| Ícono | Destino |
|-------|---------|
| 🏠 Casa | `index.html` — Inicio |
| 👤 Persona | `perfil.html` — Mi cuenta |
| 🔍 Catálogo | `catalogo.html` — Catálogo |
| 🛍️ Carrito | `historial.html` — Pedidos |

#### Mockup — Sidebar

> El boceto muestra el menú desplegable lateral con los cuatro ítems alineados verticalmente: Inicio, Mi cuenta, Catálogo, Pedidos, cada uno con su ícono a la izquierda.

![Mockup Sidebar](mockup_sidebar.png)

---

### 4.  Carrito — `carrito.html`

Muestra los productos que el usuario ha agregado:
- **Ítem 1:** Lápiz HB — Ref: 288 — $2.000
  - Controles de cantidad: `−`, número, `+`
- **Ítem 2:** Cuaderno — Ref: 552 — $3.000
  - Controles de cantidad: `−`, número, `+`
- **Resumen de totales:**
  - Subtotal: $5.000
  - IVA: $0
  - **Total: $5.000**
- Botón **"Proceder al pago"** → redirige a `checkout.html`

#### Mockup — Carrito

> El boceto detalla las tarjetas de producto con imagen, nombre, referencia y controles de cantidad a la izquierda, y el precio a la derecha. Abajo aparece el bloque de totales con Subtotal, Impuestos y Total, y el botón de pago.

![Mockup Carrito](mockup_carrito.png)

---

### 5. 💳 Checkout — `checkout.html`

Proceso de finalización de compra dividido en tres secciones:

**Sección 1 — Envío:**
- Nombre Completo
- Dirección
- Ciudad

**Sección 2 — Método de Pago:**
- 💳 Visa
- 💳 MasterCard
- 💰 PayPal

**Sección 3 — Resumen de la Orden:**
- Lápiz HB × 1 → $2.000
- Cuaderno × 1 → $3.000
- **Total: $5.000**

Botón final: **"Pagar $5.000"**

#### Mockup — Checkout

> El boceto muestra los campos de envío (nombre, dirección, ciudad) como inputs con placeholders, luego los tres métodos de pago como opciones de radio con íconos, seguidos del resumen de ítems y el botón de pago al fondo.

![Mockup Checkout](mockup_checkout.png)

---

### 6. Historial de Pedidos — `historial.html`

Lista de órdenes pasadas con su estado:

| # Orden | Precio | Fecha | Estado |
|---------|--------|-------|--------|
| #12345 | $125.500 | 15 Oct, 2023 | 🟢 Entregado |
| #12344 | $89.999 | 12 Oct, 2026 | 🟡 En camino |
| #12343 | $210.000 | 05 Oct, 2026 | 🔴 Cancelado |

Cada tarjeta incluye un enlace **"Ver detalle"**.

####  Mockup — Historial

> El boceto muestra tres tarjetas de pedido apiladas verticalmente. Cada una tiene el estado (Entregado ✓, En camino 🚚, Procesando 🔄), número de orden, fecha y total. Un botón `>` indica la acción de ver detalle.

![Mockup Historial](mockup_historial.png)

---

### 7.  Perfil — `perfil.html`

Vista del perfil de usuario con:

**Información del usuario:**
- Foto de perfil
- Nombre: Heiling León
- Usuario: @heilingleon
- Miembro desde el 15 de marzo de 2026
- Ubicación: Floridablanca - Santander
- Botón **"Editar Perfil"**

**Menú de cuenta:**
- 🕐 Historial de actividades → `historial.html`
- ⚙️ Configuraciones → `configuraciones.html`
- 📍 Direcciones → `direcciones.html`
- 🚪 Cerrar sesión → `index.html`

####  Mockup — Perfil

> El boceto muestra el avatar circular en la parte superior, debajo el nombre del usuario y datos (usuario, fecha de membresía, ubicación), el botón de editar, y las opciones de cuenta como bloques/filas con íconos a la izquierda.

![Mockup Perfil](mockup_perfil.png)

---

### 8.  Carrito Vacío — `vacio.html`

Vista alternativa cuando no hay productos en el carrito:
- Ícono grande de carrito tachado (con X).
- Texto: **"Tu carrito está vacío"**
- Subtexto: *"Cuando agregues productos aparecerán aquí."*
- Botón: **"Explorar productos"** → redirige a `catalogo.html`

####  Mockup — Carrito Vacío

> El boceto muestra el header de Campus Shop con íconos de carrito y alerta, luego en el centro el ícono de carrito vacío con X, el mensaje de estado y el botón de explorar productos.

![Mockup Vacio](mockup_vacio.png)

---

### 9.  Detalle de Producto *(página referenciada en mockup)*

Pantalla planificada en el mockup (no incluida como archivo independiente aún):
- Imagen grande del producto.
- Nombre y precio: ej. **Mochila Clásica — $70.000**
- Descripción del producto.
- Selector de **Color**: Negro, Marrón, Blanco.
- Botón **"Agregar al carrito"**.
- Sección de **Productos relacionados** (carrusel inferior).

#### Mockup — Detalle de Producto

> El boceto muestra la imagen del producto centrada, debajo el nombre y precio, una descripción corta, los botones de color como chips, el CTA de agregar al carrito, y un carrusel con productos similares.

![Mockup Detalle](mockup_detalle.png)

---

##  Componentes comunes

### Header
Presente en todas las vistas (excepto login). Contiene:
- Botón hamburger (abre sidebar con checkbox CSS).
- Logo con imagen y nombre "Campus Shop".
- Íconos de navegación rápida: carrito y (en inicio) botón de sesión.

### Sidebar
Menú lateral deslizable activado por el checkbox `#menu-toggle`. Incluye los cuatro accesos principales.

---

##  Tecnologías usadas

- **HTML5** — estructura de todas las vistas.
- **CSS3** — estilos independientes por vista (`css/nombre.css`).
- **SVG inline** — íconos vectoriales sin dependencias externas.

---

## 👩Autora

**Heiling León** — @heilingleon  
Proyecto Campus Shop · 2026  
Floridablanca, Santander, Colombia