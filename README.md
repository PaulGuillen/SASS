# Proyecto SASS

Este proyecto utiliza **SASS** como preprocesador de CSS para manejar los estilos de manera más eficiente y organizada. A continuación, se describe todo lo que se ha aprendido y utilizado en este proyecto.

## ¿Qué es SASS?
SASS (Syntactically Awesome Stylesheets) es un preprocesador de CSS que extiende sus funcionalidades, permitiendo escribir código más eficiente y fácil de mantener. Algunas de las características clave de SASS son:
- Uso de **variables** para almacenar valores reutilizables como colores, tamaños, y fuentes.
- **Anidamiento** de selectores, que facilita la lectura y el mantenimiento del código.
- **Mixins** para reutilizar bloques de código.
- **Partials** y **@import** para dividir los archivos CSS en módulos más pequeños y manejables.
- Funciones como `darken()`, `lighten()` o `color.scale()` para manipular colores.

### Variables
Las **variables** permiten almacenar valores que pueden ser reutilizados a lo largo de los estilos.

Ejemplo de archivo `_Colors.scss`:

```scss
// Colores principales
$primary-color: #3498db;
$secondary-color: #2ecc71;
$accent-color: #e74c3c;

// Colores de fondo
$background-color: #ecf0f1;
$header-background: #34495e;

// Colores de texto
$text-color: #2c3e50;
$light-text: #bdc3c7;

nav {
  background-color: $primary-color;
  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: space-around;
    
    li {
      padding: 10px;
      
      a {
        color: white;
        text-decoration: none;
      }
    }
  }
}
```
### Aplicación de las variables:
```scss
nav {
  background-color: $primary-color;
}
```

### Anidamiento (Selectores)
Ejemplo de archivo `_Menu.scss`:

```scss
nav {
  background-color: $primary-color;

  ul {
    list-style-type: none;

    li {
      padding: 10px;

      a {
        color: white;
        text-decoration: none;
      }
    }
  }
}
```

### Anidamiento con Ampersand (&)
_Referencia al selector padre dentro de un bloque anidado, ideal para manejar pseudoclases y estados._
_Aquí, &:hover aplica estilos cuando el botón es hovered, y &.active cuando tiene la clase active._

```scss
button {
  background-color: $secondary-color;

  &:hover {
    background-color: darken($secondary-color, 10%);
  }

  &.active {
    background-color: $primary-color;
  }
}
```

### Importación (Modularidad/Partials)
Ejemplo de archivo `styles.scss`:

_Cada archivo parcial (como _Variables.scss, _Header.scss, etc.) contiene su propio conjunto de estilos. Esto mejora la organización y el mantenimiento del código._

```scss
@import 'Colors';
@import 'Variables';
@import 'Header';
@import 'Menu';
@import 'Footer';
```
