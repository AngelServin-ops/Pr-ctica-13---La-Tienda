# Práctica 13 - La Tienda: Composición, Eventos y Estado

Proyecto desarrollado con **React**, **TypeScript** y **Vite** para la materia de Tópico de Aplicaciones Web (ITSON).

---

## Descripción

Aplicación interactiva de tienda en línea que utiliza el concepto de composición de componentes en React, paso de funciones mediante `props`, y manejo de estado local (`useState`).

### Funcionalidades
- **Layout genérico:** Estructura fija con encabezado, contenido principal y pie de página.
- **Catálogo de productos:** Visualización dinámica de productos con nombre, imagen, precio y existencias.
- **Filtrado por categoría:** Botones interactivos para filtrar entre *todas*, *calzado*, *ropa* y *accesorios*.
- **Carrito de compras:** Adición de productos al carrito controlando stock agotado y calculando total acumulado y piezas en tiempo real.

---

## Tecnologías Utilizadas

- **React 18 / 19**
- **TypeScript**
- **Vite**
- **CSS3**

---

## Cuestionario de la Práctica

### Ejercicio 1: El marco de la página
> **Pregunta:** ¿Por qué el `Layout` no necesita saber que es una tienda?
>
> **Respuesta:** El componente Layout funciona únicamente como una plantilla o envoltorio agnóstico. Su papel se limita a estructurar la maqueta base (como el header, footer y el área principal) y renderizar el contenido dinámico a través de children. Al estar desacoplado de los datos del catálogo y de la lógica de negocio, se convierte en una pieza completamente reutilizable para cualquier sección de la aplicación.

---

### Ejercicio 2: El catálogo
> **Pregunta:** ¿Qué pasa si escribes `onClick={onAgregar(producto)}` sin la flecha?
>
> **Respuesta:** Al omitir la función flecha, la función se invoca inmediatamente durante el proceso de renderizado en lugar de registrarse como un manejador de eventos a la espera del clic. Si esa ejecución actualiza el estado de React, desencadenará un renderizado en cadena que generará un bucle infinito (infinite re-render) y congelará la aplicación.

---

### Ejercicio 3: Filtrar y agregar al carrito
> **Pregunta:** ¿Por qué con `carrito.push(...)` el contador no se mueve y no sale ningún error?
>
> **Respuesta:** React determina cuándo actualizar la vista comparando las referencias en memoria del estado (shallow comparison). El método .push() altera el arreglo original directamente sin cambiar su dirección en memoria; como la referencia sigue siendo idéntica, React asume que no hubo cambios y omite el re-renderizado. No se lanza ningún error en consola porque modificar arreglos con .push() es una operación nativa y válida en JavaScript.

---
