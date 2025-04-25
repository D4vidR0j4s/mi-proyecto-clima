# CORRECCIÓN DE BUENAS PRÁCTICAS EN ClimApp

## 1. ¿Qué mala práctica identifiqué?

Definición de variables CSS custom properties (`--color-success`, `--color-warning`, etc.) que no se usan en ninguna parte del proyecto, ausencia de un archivo `.gitignore` y nombre poco intuitivo del archivo CSS principal (`index.css`).

## 2. ¿Por qué es considerada mala práctica?
- Variables no utilizadas inflan el CSS y crean deuda técnica.
- Ausencia de `.gitignore` puede exponer archivos confidenciales o irrelevantes al repositorio remoto.
- El nombre `index.css` no refleja claramente que contiene los estilos principales de la aplicación, lo que puede confundir a desarrolladores nuevos.

## 3. ¿Cómo lo solucioné?
1. Eliminé del bloque `:root` todas las CSS custom properties sin uso.
2. Añadí un archivo `.gitignore` para excluir dependencias, logs y variables de entorno.
3. Renombré `index.css` a `estilos.css` y actualicé la línea `<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />` en `index.html` por `<link rel="stylesheet" href="estilos.css">` por una parte para mantener coherencia semántica en los nombres, y por otra más importante era que en un principio directamente no se tomaba el arhivo de estilos (estaba mal referenciado) por lo que no se mostraban los mismos en la página, tras esta diminuta modificación se solucionó.

## 4. Beneficios de la solución
- Reducción del tamaño y complejidad del CSS.
- Facilita la lectura y mantenimiento del código.
- Protege información sensible y mantiene el repositorio limpio.
- Mejora la semántica y claridad de la estructura de archivos, ayudando a identificar rápidamente el propósito de cada recurso.