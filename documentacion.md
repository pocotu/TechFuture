# Documentación del Sitio Web TechFuture

## Introducción

Este documento proporciona información detallada sobre la implementación y funcionamiento del sitio web TechFuture. El sitio está desarrollado como una landing page moderna para una empresa de tecnología, utilizando HTML5 y CSS3 con un enfoque en diseño responsive y experiencia de usuario.

## Estructura del Proyecto

```
TechFuture/
├── index.html          # Estructura principal del sitio
├── styles.css          # Estilos y diseño visual
└── img/                # Directorio de imágenes
    ├── main.jpg        # Imagen de fondo principal
    ├── IA.jpg          # Imagen para sección de IA
    ├── desarrolloWeb.jpg # Imagen para sección de Desarrollo Web
    └── cloudComputing.jpg # Imagen para sección de Cloud Computing
```

## Estructura HTML (index.html)

El sitio está desarrollado como una aplicación de página única (SPA) con navegación por anclas. La estructura HTML se divide en las siguientes secciones principales:

### 1. Header y Navegación

```html
<header>
    <nav class="navbar">
        <div class="logo">
            <h1>TechFuture</h1>
        </div>
        <ul class="nav-links">
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#mision">Misión</a></li>
            <li><a href="#proyectos">Proyectos</a></li>
            <li><a href="#unete">Únete</a></li>
        </ul>
    </nav>
</header>
```

- Barra de navegación fija en la parte superior
- Logo de la empresa
- Enlaces de navegación que dirigen a diferentes secciones de la página

### 2. Banner Principal

```html
<section id="inicio" class="banner">
    <div class="banner-content">
        <h2>Innovación Tecnológica para el Futuro</h2>
        <p>Transformando ideas en realidad digital</p>
        <a href="#mision" class="cta-button">Conoce más</a>
    </div>
</section>
```

- Sección de presentación con altura completa
- Título principal y subtítulo
- Botón de llamada a la acción que navega a la sección de misión

### 3. Sección de Misión

```html
<section id="mision" class="mision">
    <div class="mision-content">
        <h2>Nuestra Misión</h2>
        <p>En TechFuture, nos dedicamos a desarrollar soluciones tecnológicas innovadoras...</p>
    </div>
</section>
```

- Descripción de la misión y visión de la empresa
- Contenido centrado para mejorar la legibilidad

### 4. Sección de Proyectos

```html
<section id="proyectos" class="proyectos">
    <h2>Nuestros Proyectos</h2>
    <div class="proyectos-grid">
        <!-- Tarjetas de proyectos -->
    </div>
</section>
```

- Presentación de los tres servicios principales en un diseño de cuadrícula
- Cada tarjeta incluye una imagen, título y descripción breve

### 5. Formulario de Contacto

```html
<section id="unete" class="unete">
    <h2>Únete a TechFuture</h2>
    <form class="formulario">
        <!-- Campos del formulario -->
    </form>
</section>
```

- Formulario para que los visitantes contacten con la empresa
- Incluye campos para nombre, correo electrónico y mensaje

### 6. Footer

```html
<footer>
    <p>&copy; 2024 TechFuture. Todos los derechos reservados.</p>
</footer>
```

- Información de copyright y derechos reservados

## Estilos CSS (styles.css)

El archivo CSS está organizado en secciones que corresponden con los elementos del HTML:

### 1. Variables y Reset

```css
:root {
  --color-dark-blue: #213A57;
  --color-teal: #0B6477;
  --color-turquoise: #14919B;
  --color-bright-turquoise: #0AD1C8;
  --color-mint: #45DFB1;
  --color-light-green: #80ED99;
  
  --gradient-primary: linear-gradient(to right, var(--color-dark-blue), var(--color-light-green));
  --gradient-vertical: linear-gradient(to bottom, var(--color-dark-blue), var(--color-bright-turquoise));
}
```

- Utiliza variables CSS para mantener una paleta de colores coherente
- Reset básico para eliminar márgenes y rellenos predeterminados
- Box-sizing configurado para facilitar el diseño de layout

### 2. Estilo del Banner

```css
.banner {
    height: 100vh;
    background: linear-gradient(rgba(33, 58, 87, 0.7), rgba(10, 209, 200, 0.7)),
                url('img/main.jpg') center/cover;
    background-attachment: fixed;
    position: relative;
    /* más propiedades... */
}

.banner::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: url('img/main.jpg') center/cover no-repeat;
    filter: blur(5px);
    z-index: -1;
}
```

- Usa una técnica de capa superpuesta para crear un efecto de desenfoque
- El gradiente semitransparente sobre la imagen para mejorar el contraste del texto
- La imagen de fondo tiene un efecto de parallax (background-attachment: fixed)

### 3. Tarjetas de Proyectos

```css
.proyecto-card {
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
}

.proyecto-card:hover {
    transform: translateY(-5px);
}
```

- Tarjetas con efecto de elevación al pasar el cursor
- Transiciones suaves para mejorar la interactividad
- Imágenes con efecto de zoom al hover

### 4. Diseño Responsive

```css
@media (max-width: 768px) {
    .navbar {
        flex-direction: column;
        gap: 1rem;
    }
    
    /* Más reglas responsive... */
}
```

- Media queries para adaptarse a dispositivos móviles
- Cambios en la disposición de elementos cuando la pantalla es pequeña

## Paleta de Colores

La paleta de colores utiliza una combinación de azules y verdes que transmiten tecnología, innovación y frescura:

| Color | Código Hex | Uso |
|-------|------------|-----|
| Azul oscuro | #213A57 | Texto principal, cabeceras |
| Teal | #0B6477 | Elementos secundarios, enlaces |
| Turquesa | #14919B | Acentos, hover states |
| Turquesa brillante | #0AD1C8 | Botones, call-to-action |
| Menta | #45DFB1 | Elementos decorativos |
| Verde claro | #80ED99 | Elementos destacados |

## Técnicas de Diseño Implementadas

1. **Parallax y Desenfoque**: 
   - La imagen de fondo principal utiliza un efecto de parallax y desenfoque para crear profundidad.
   - Se aplica un fondo semitransparente detrás del texto para mejorar la legibilidad.

2. **Micro-interacciones**: 
   - Animaciones sutiles en botones y tarjetas al pasar el cursor.
   - Transiciones suaves para mejorar la experiencia del usuario.

3. **Diseño Responsivo**: 
   - Layout fluido que se adapta a diferentes tamaños de pantalla.
   - Uso de grid y flexbox para una disposición flexible de elementos.

4. **Accesibilidad**:
   - Contraste adecuado entre texto y fondo.
   - Jerarquía clara de encabezados.
   - Enlaces y botones con estados visuales distintivos.

## Implementación de JavaScript (Futuro)

Actualmente, el sitio no utiliza JavaScript activo, pero podría mejorarse con:

- Validación del formulario de contacto
- Animaciones de desplazamiento suave
- Carrusel para mostrar más proyectos
- Modo oscuro / claro

## Conclusión

El sitio web TechFuture presenta un diseño moderno y atractivo que se alinea con la imagen de una empresa de tecnología innovadora. El uso de técnicas actuales de CSS como variables, flexbox, grid y efectos visuales crea una experiencia de usuario fluida y agradable, manteniendo un código limpio y mantenible. 