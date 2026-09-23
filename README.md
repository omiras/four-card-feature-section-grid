# Sección de cuatro tarjetas con CSS Grid

Completa la distribución de cuatro tarjetas: una columna en móvil, dos columnas a partir de 680 px y una composición de tres columnas a partir de 1200 px. El HTML, los iconos, colores y tipografía ya están preparados. Trabaja en [`css/main.css`](css/main.css), siguiendo sus comentarios **Ejercicio 0**, **Ejercicio 1** y **Ejercicio 2**. 

Puedes ver una [demo funcional](https://four-card-feature-section-hfeblg9uh.now.sh/)

## Diseños de referencia

| Móvil | Escritorio |
| --- | --- |
| ![Diseño móvil](design/mobile-design.jpg) | ![Diseño de escritorio](design/desktop-design.jpg) |



## Cómo trabajar

Abre `index.html` en el navegador y `css/main.css` en tu editor. Localiza los tres comentarios de ejercicio. Haz un cambio pequeño cada vez, guarda y recarga la página. Cambia el ancho de la ventana para comprobar las tres disposiciones.

Necesitarás selectores CSS, `max-width`, Grid y consultas de medios. La consulta a partir de 680 px ya está escrita; la de 1200 px debes crearla tú. Conserva el HTML y los estilos de las tarjetas.

## Ejercicio 0: ancho de las tarjetas

**Objetivo:** limitar el ancho del bloque de tarjetas a 375 px mientras aparecen en una sola columna y mantenerlo centrado. Trabaja en la regla `.cards`.

**Comprueba:** en una ventana estrecha las tarjetas forman una columna y el bloque deja espacio a ambos lados.

<details>
<summary>Pista: código incompleto y explicación</summary>

```css
.cards {
    /* Conserva los estilos existentes. */
    max-width: /* límite indicado en el ejercicio */;
    margin-left: /* valor que centra un bloque */;
    margin-right: /* el mismo valor */;
}
```

`max-width` limita el ancho sin obligar al bloque a medir siempre lo mismo. Los márgenes laterales pueden repartir el espacio libre. Piensa si este límite deberá cambiar cuando aparezcan varias columnas.

</details>

## Ejercicio 1: cuadrícula de 2 × 2

**Objetivo:** a partir de 680 px, mostrar dos tarjetas por fila y dos filas. Usa la consulta de medios existente. Las tarjetas deben conservar el orden del HTML.

**Comprueba:** por debajo de 680 px hay una columna; a partir de esa anchura aparecen dos columnas con separación entre tarjetas.

<details>
<summary>Pista: código incompleto y explicación</summary>

```css
@media (min-width: 680px) {
    .cards {
        display: grid; /* Ya está escrito en main.css. */
        grid-template-columns: repeat(2, /* reparto del ancho */);
        gap: /* espacio entre tarjetas */;
        max-width: /* ancho adecuado para dos columnas */;
    }
}
```

`grid-template-columns` define las columnas. Grid coloca automáticamente las cuatro tarjetas en el orden del HTML, por lo que aquí no necesitas posicionarlas una a una. El límite de ancho del ejercicio 0 puede resultar demasiado pequeño para dos columnas.

</details>

## Ejercicio 2: composición de escritorio

**Objetivo:** desde 1200 px, disponer tres columnas. Supervisor queda a la izquierda; Team Builder y Karma se apilan en el centro; Calculator queda a la derecha. Las dos tarjetas laterales se centran verticalmente respecto al conjunto central.

**Comprueba:** la posición coincide con la imagen de escritorio. Al estrechar la ventana reaparecen la cuadrícula de 2 × 2 y después la columna única. Las tarjetas no se solapan.

<details>
<summary>Pista 1: planifica las zonas</summary>

Dibuja tres columnas. La central tiene dos posiciones, una encima de otra. Las tarjetas laterales pueden abarcar la altura de ambas. Decide qué líneas de fila y columna delimitan cada tarjeta antes de escribir CSS.

</details>

<details>
<summary>Pista 2: código incompleto y explicación</summary>

```css
@media (min-width: 1200px) {
    .cards {
        grid-template-columns: repeat(3, /* ancho de cada columna */);
        align-items: /* valor para centrar los elementos */;
        max-width: /* espacio para tres tarjetas */;
    }

    .card-supervisor {
        grid-column: 1;
        grid-row: /* filas que abarca */;
    }

    .card-team-builder {
        grid-column: 2;
        grid-row: /* posición superior */;
    }

    .card-karma {
        grid-column: 2;
        grid-row: /* posición inferior */;
    }

    .card-calculator {
        grid-column: 3;
        grid-row: /* filas que abarca */;
    }
}
```

`grid-column` y `grid-row` sitúan cada tarjeta en la cuadrícula. Una tarjeta puede ocupar una fila o abarcar varias. `align-items` controla la alineación de las tarjetas dentro de sus áreas; observa su efecto en las dos laterales.

</details>

## Revisión final

- Comprueba la página cerca de 375 px, 800 px y 1440 px: ¿ves una columna, dos columnas y la composición de escritorio?
- ¿Las cuatro tarjetas conservan texto e iconos?
- ¿Alguna tarjeta queda demasiado estrecha, se solapa o sale de la pantalla?
- Al cambiar el ancho en ambos sentidos, ¿se aplica la disposición correspondiente?

## Recursos

- [Introducción a CSS Grid en MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Grids)
- [Referencia de `grid-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column) y [`grid-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row) en MDN
- [Consultas de medios en MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Media_queries)
