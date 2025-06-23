# FakeStore-API

Este proyecto es una **tienda online ficticia** construida en HTML, CSS y JavaScript puro, que utiliza la [FakeStore API](https://fakestoreapi.com/) para mostrar productos, filtrarlos, ordenarlos y permitir al usuario simular compras a través de un carrito persistente en `localStorage`.

---

## 🚚 Características principales

- **Catálogo de productos:** Visualización de productos en formato de cartas.
- **Filtrado por categorías:** Ropa de hombre, ropa de mujer, joyería y electrónicos.
- **Búsqueda en tiempo real:** Filtra productos por nombre mientras escribes.
- **Ordenamiento flexible:** Ordena por mayor precio, menor precio o mejor calificación.
- **Carrito de compras:** Añade productos, elimina, visualiza el total y simula el pago.
- **Persistencia del carrito:** El carrito se mantiene aún si cierras o recargas la página.
- **Animación de carga:** Visual feedback agradable mientras se cargan los productos.
- **Responsive:** Se adapta a móviles, tablets y escritorio.

---

## 📂 Estructura de archivos

```
/
├── index.html
├── style.css
├── JS/
│   └── main.js
├── IMG/
│   ├── logo.png
│   ├── hombre.jpg
│   ├── mujer.jpg
│   ├── joyeria.jpg
│   ├── electrodomesticos.jpg
│   └── carrito.png
```


## ⚙️ ¿Cómo funciona?

1. **Carga inicial**:  
   Al ingresar, se muestra un loader animado mientras se cargan los productos desde la FakeStore API.

2. **Visualización y navegación**:  
   Los productos aparecen en cartas con imagen, título, precio y calificación. Puedes buscar por título, filtrar por categoría, o cambiar el orden (precio/calificación).

3. **Gestión del carrito**:  
   Puedes añadir productos haciendo clic en "Añadir al carrito". El carrito se almacena en `localStorage`. Puedes ver el carrito en cualquier momento, eliminar productos individuales o vaciarlo al simular el pago.

4. **Persistencia**:  
   El carrito no se borra al actualizar o cerrar la pestaña, a menos que pulses "Pagar".

---

## 🧩 Funcionalidades detalladas

- **Filtrado por categoría:**  
  Haz clic en una de las imágenes de categoría para ver solo esos productos.

- **Búsqueda dinámica:**  
  Escribe en el campo "Buscar..." y los productos se filtrarán automáticamente según el texto ingresado.

- **Ordenamiento:**  
  Utiliza el select para ordenar los productos por precio mayor, menor o calificación.

- **Carrito de compras:**  
  - Haz clic en el ícono del carrito (footer) para ver tu carrito.
  - El modal muestra los productos agregados, con opción de eliminar individualmente.
  - El botón "Pagar" vacía el carrito y muestra un mensaje de agradecimiento.

---

## 🛠️ Instalación y uso

1. **Descarga o clona este repositorio:**
   ```bash
   git clone https://github.com/Davisson-Adriel/FakeStore-API.git
   ```
2. **Abre `index.html`** directamente en tu navegador.

> **No se requiere servidor, backend ni dependencias adicionales.**

---

## 📦 Recursos

- **FakeStore API:** [https://fakestoreapi.com/](https://fakestoreapi.com/)

---

## Maquetación Planeada

![Escritorio](image.png)
![Carrito de compra escritorio](image-1.png)
![Movil](image-2.png)
![Carrito de compra movil](image-4.png)

Se presenta la maquetación inicialmente planteada; sin embargo, se realizaron ajustes al boceto con el fin de lograr un diseño más elegante y coherente con sus componentes. Además, el carrito de compras fue trasladado de un archivo HTML independiente a un sistema implementado con JavaScript, permitiendo mostrar su contenido dentro del mismo HTML.

---

## ✨ Autor

- Davisson-Adriel  
- [GitHub](https://github.com/Davisson-Adriel)
- [Pages](https://davisson-adriel.github.io/FakeStore-API/)

