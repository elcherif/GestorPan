# GestorPan

**GestorPan** es una aplicación web **de una sola página** (SPA) contenida en un único fichero (`index.html`) para **crear, calcular y gestionar recetas de panificación** usando el método de **porcentaje del panadero (Baker’s Percentage)**.

Está pensada para:
- Mantener una biblioteca sencilla de recetas (crear, editar, duplicar y eliminar).
- Convertir pesos a % del panadero y **recalcular cantidades** al cambiar la base de harina.
- Estandarizar fórmulas de **pan, pizza y masa madre/prefermentos**, contabilizando la contribución de harina/agua del starter.
- Importar ingredientes rápidamente desde **texto libre** (Modo B) normalizando formatos y unidades comunes.

## Qué puedes hacer

### 1) Gestión de recetas
- Crear y guardar recetas en el navegador.
- Editar metadatos (nombre, tipo/categoría, notas).
- Buscar por **título** y por **nombres de ingredientes**.
- Limpiar búsqueda y restablecer filtros.

### 2) Cálculo de % del panadero
- Cálculo automático del % por ingrediente respecto a la base de harina.
- Escalado de fórmulas cambiando el peso objetivo de harina (o base equivalente), actualizando las cantidades.
- Métricas habituales de panificación (por ejemplo, **hidratación**).

### 3) Soporte de masa madre / prefermentos
- Marcar un prefermento/starter para que su harina y agua **cuenten en el total de harina y en la hidratación**.
- Mostrar hidratación y % del panadero “efectivos” incluyendo contribuciones del starter.

### 4) Parser de ingredientes desde texto libre (Modo B)
- Pegar líneas de ingredientes y parsear cantidades como gramos, mililitros, cucharaditas, pizcas, huevos, etc.
- Ignorar cabeceras tipo “Para la masa:” y conservar líneas no parseables como notas.

### 5) Extras de usabilidad
- Autocompletado de ingredientes.
- Búsqueda con “debounce” para filtrar de forma fluida.
- Vista de impresión compacta.

## Cómo usar (guía rápida)

### A. Abrir la aplicación
1. Clona el repo o descarga el proyecto.
2. Abre `index.html` en un navegador moderno (Chrome/Edge/Firefox).
3. La app funciona sin instalación ni build.

### B. Crear una receta desde cero
1. Pulsa **Nueva receta**.
2. Rellena **nombre**, **tipo** (por ejemplo: pan/pizza) y **notas** si quieres.
3. Añade ingredientes (harinas, agua, sal, levadura, etc.) con sus cantidades.
4. Marca la(s) **harina(s)** como base para el cálculo.
5. Revisa el **% del panadero** y la **hidratación** calculada.
6. Guarda la receta: quedará persistida en `localStorage`.

### C. Escalar una receta
1. Abre la receta.
2. Cambia el valor de la **base de harina** (objetivo) o el control equivalente de escalado.
3. Comprueba que todas las cantidades se recalculan manteniendo proporciones.

### D. Usar masa madre / prefermento
1. Añade el ingrediente correspondiente al starter/prefermento (con su peso).
2. Configura su hidratación/composición si la UI lo solicita.
3. Verifica las métricas “efectivas” (harina total, hidratación real, % ajustados) que incluyen el starter.

### E. Importar ingredientes pegando texto (Modo B)
1. Entra en **Modo B / Texto libre**.
2. Pega una lista (una línea por ingrediente), por ejemplo:
   - `500 g harina`
   - `350 g agua`
   - `10 g sal`
3. Ejecuta el parseo/importación.
4. Revisa las líneas no interpretadas (se guardan como notas).

### F. Buscar, filtrar e imprimir
- Usa el buscador para localizar recetas por nombre o por ingredientes.
- Limpia filtros/búsqueda cuando quieras volver a ver todo.
- Usa la opción de **imprimir** para obtener una ficha compacta.

## Archivos
- `index.html`: aplicación completa (UI, estilos y lógica).
- `CHANGELOG.md`: historial de cambios.
- `README.md`: documentación.

## Almacenamiento de datos
Los datos se guardan localmente en el navegador mediante `localStorage` (no requiere backend).