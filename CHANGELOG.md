# Registro de cambios

En este archivo se documentarán todos los cambios relevantes de este proyecto.

## 2026-03-30

### Añadido
- Se creó el README del proyecto (`README.md`).
- Se añadió `index.html`, que implementa la aplicación web GestorPan para gestionar recetas con **porcentaje del panadero**.
- Se añadió una biblioteca inicial de recetas de ejemplo (60+), con un mecanismo de versionado para cargar nuevas muestras sin duplicar las existentes.
- Se añadieron sugerencias de autocompletado de ingredientes.
- Se añadió una acción de “Limpiar filtros” y un control para “limpiar búsqueda”.
- Se añadió un nuevo tipo de receta: **pizza**.
- Se añadieron reglas de maquetación compacta/optimizada para impresión.
- Se añadió soporte para masa madre/prefermentos, con cálculos de hidratación y de harina/totales que tienen en cuenta las contribuciones del starter.

### Cambiado
- Se mejoró la edición de ingredientes para que los recálculos no interfieran mientras se escribe.
- Se mejoró el parser de ingredientes desde texto libre (Modo B) para manejar mejor formatos comunes (gramos/ml/cucharaditas/pizcas/huevos, etc.), ignorar cabeceras de sección y conservar como notas las líneas no parseables.
- Se mejoró la búsqueda para que también encuentre por nombre de ingrediente, además de por título de receta.
- Se aplicó “debounce” a la entrada de búsqueda para reducir rerenders innecesarios.
- Se aclaró la conversión de huevos a gramos usada por el parser.
- Se ajustaron los cálculos del % del panadero para reflejar la base de harina efectiva cuando hay harina aportada por la masa madre.

### Notas
- Algunos commits del 2026-03-30 son merges de PRs que consolidan los cambios anteriores; el resultado final en `main` queda reflejado aquí.