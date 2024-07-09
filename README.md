# Curso SASS

## Instalacion

Instalar Sass en el proyecto

`npm i sass -D -E`

Instalar Sass globalmente

`npm i -g sass`

## Comenzando

Los archivos de sass tiene la extension .scss.

Comando que indica que sass debe leer los archivos que estan dentro de la carpeta llamada sass y que debe convertir el codigo en css

`sass --watch sass:css`

Esto estara mirando por cambios dentro de la carpeta sass y creara un archivo compilado en css en css/style.css.

La ruta del archivo css creado es el que debe referenciarce en el archivo html.

## Variables

Se definen con el simbolo $ y se puede almacenar cualquier valor: colores, reglas, etc.

```css
$color-1: green;

h2 {
  color: $color-1;
}
```

## Partials

Son sub-archivos con los que se puede modularizar el codigo.

Por ejemplo se puede tener un partial para el nav, el footer, etc.

Un archivo partial se define dentro de la carpeta sass y su nombre empieza con \_.

`_header.scss`

Los partials no se compilan, pero su codigo puede ser compilado si se lo importa en el archivo principal de sass.

Importar un partial:

```css
@use "header";
```

Los partials pueden ser usados para definir todas las variables en un solo archivo para luego ser usadas en otros archivos sass.

Para utilizar una variable definida en un partial, primero se debe importar el partial

```css
@use "variables";
```

luego se utiliza la variable anteponiendo el namespace con un punto.

```css
h2 {
  color: variables.$color-1;
}
```

## Parent element

En sass es posible referenciar al elemento padre con & para hacer nesting.

```css
.nav {
  color: black;

  &__container: {
    color: white;

    &--active: {
      color: green;
    }
  }
}
```

## Interpolacion

Sirve para utilizar variables que tiene como valor una propiedad o selectores.

Se escribe con un numeral y llaves #{}.

```css
$display: "display";

$selector: ".header";

#{selector} {
  #{$display}: flex;
}
```


