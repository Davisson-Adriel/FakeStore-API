# Análisis de Decisiones de Diseño de Interfaz y Experiencia de Usuario

## 1. Decisiones de Diseño de Interfaz

La interfaz está pensada para ser **intuitiva, visualmente atractiva y funcional**. Se optó por el uso de cartas para mostrar los productos, ya que este formato facilita la comparación visual entre artículos y es ampliamente reconocido por los usuarios en tiendas online.
Los botones de acciones (añadir al carrito, pagar, eliminar del carrito) están claramente identificados y se encuentran junto a cada producto o dentro del modal del carrito, permitiendo interacciones rápidas y sin ambigüedades.

La experiencia de usuario se optimiza mediante:
- **Cargas simuladas y loader animado:** dan feedback visual durante el fetch de productos, evitando la percepción de bloqueos o errores.
- **Modal para el carrito:** permite revisar, eliminar productos y pagar sin abandonar la página principal, reduciendo fricción en el proceso de compra.
- **Búsqueda en tiempo real:** el filtrado por texto se realiza dinámicamente sobre los productos ya cargados, ofreciendo respuestas inmediatas a las consultas del usuario.
- **Persistencia del carrito:** el uso de `localStorage` asegura que el usuario no pierda su selección de productos aunque recargue la página.

## 2. Estructura de Datos

- **Productos:**  
  Los productos se obtienen desde la API y se manejan como objetos con campos estructurados (`id`, `title`, `price`, `image`, `category`, `rating`, etc.).

- **Carrito:**  
  El carrito se representa como un **array de objetos** en JavaScript:
  ```js
  [
    { producto: "Nombre del producto", precio: 29.99 },
    ...
  ]
  ```
  Este array se almacena y recupera de `localStorage` bajo la clave `"carrito"`, permitiendo persistencia entre sesiones o recargas.

## 3. Filtros y Ordenamientos: Justificación de Usabilidad

- **Filtrado por categorías:**  
  Permite a los usuarios reducir la cantidad de información visualizada a solo la que les interesa, mejorando la eficiencia de navegación.

- **Ordenamiento por precio o puntuación:**  
  El usuario puede priorizar productos más baratos, más caros o mejor valorados según su intención de compra, facilitando encontrar la mejor opción rápidamente.

- **Búsqueda por nombre:**  
  Agiliza la localización de productos específicos.

---

## 4. ¿Por qué esta estructura?

La estructura de este código busca la **modularidad** y la **claridad**. Cada función resuelve una acción específica y bien definida, lo que facilita el mantenimiento y la escalabilidad del código. Separar responsabilidades ayuda a depurar errores, entender el flujo de datos y modificar o agregar funcionalidades sin afectar otras partes del sistema.

- **Separación de responsabilidades:** Cada función cumple un solo propósito (cargar productos, filtrar, ordenar, buscar, gestionar carrito).
- **Facilidad de integración y modificación:** Si se requiere cambiar la fuente de los productos, la interfaz de usuario o la lógica del carrito, solo es necesario modificar las funciones especificas.

## 5. ¿Para qué sirve cada parte?

### **obtenerproductor**
Carga todos los productos desde la API y los muestra en el contenedor principal. Se encarga de renderizar cada producto como una "carta" y de asociar el evento de añadir al carrito, de manera que cada evento se asocia directamente a un producto especifico lo cual permite el almacenamiento en el localStorage

### **filtrarProductos**
Filtra productos por categoría según el id del elemento seleccionado (evento). Solo muestra los productos que pertenecen a la categoría seleccionada.

### **inicio**
Muestra una pantalla de carga, oculta el contenido principal y el header temporalmente. Tras una espera simulada, revela el contenido y llama a `obtenerproductor` para cargar los productos. Permite dar una experiencia inicial más fluida.

### **ordenarProductos**
Ordena los productos por precio (mayor o menor) o por puntuación (rating) según la selección del usuario en un menú desplegable.

### **buscarproductos**
Permite filtrar los productos actualmente mostrados por coincidencia en el título.

### **agregaralcarrito**
Toma la información del producto seleccionado y lo agrega al carrito almacenado en `localStorage`. Notifica al usuario del agregado con un alert.

### **vercarrito**
Muestra el modal del carrito, permite eliminar productos y calcular el total. También limpia el carrito tras realizar el pago simulado.

### **Inicialización y variables globales**
Al cargar el documento (`DOMContentLoaded`), se asocian los eventos necesarios. La variable global `categoriaseleccionada` permite mantener el estado de la categoría activa.

## 6. ¿Cómo funciona el flujo?

1. **Al iniciar la página**, se ejecuta `inicio()`, que muestra la animación de carga y luego carga y muestra todos los productos.
2. **Filtrado por categoría:** Al hacer clic en una categoría, `filtrarProductos` carga los productos solo de esa categoría.
3. **Ordenamiento:** Al cambiar el filtro de orden, `ordenarProductos` reorganiza los productos mostrados según el criterio seleccionado.
4. **Búsqueda:** El usuario puede buscar productos por nombre, y los resultados se muestran dinámicamente.
5. **Carrito:** Los productos pueden agregarse al carrito, que se almacena en `localStorage` y puede ser visualizado por el usuario.

## 7. Justificación de elecciones técnicas

- **Fetch API:** Permite obtener datos de la API externa fácilmente y de forma asíncrona.
- **Manipulación dinámica del DOM:** Se crean y modifican nodos HTML según los datos obtenidos, brindando flexibilidad.
- **Uso de localStorage:** Permite persistencia del carrito aun cuando el usuario recarga la página.
- **Timers (`setTimeout`):** Simulan carga para mejorar experiencia de usuario, aunque en producción podría optimizarse según la velocidad real de la API.
- **Eventos dinámicos:** Los botones se asocian a eventos en el momento de creación, permitiendo que cada elemento interactúe con el usuario de forma independiente.

