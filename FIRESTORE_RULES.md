# Reglas de Seguridad para Firestore

Ve a **Firebase Console > Firestore Database > Rules** y reemplaza el contenido con esto:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Cada usuario solo puede leer/escribir sus propias recetas
    match /usuarios/{uid}/recetas/{document=**} {
      allow read, write: if request.auth.uid == uid;
    }
  }
}
```

Luego haz clic en **Publicar**.

## ¿Por qué es necesario?

Sin estas reglas, Firestore rechaza todas las operaciones (incluyendo el listener en tiempo real `onSnapshot()`), aunque uses autenticación.

## Después de publicar:

1. Recarga la app en dos navegadores.
2. Inicia sesión en ambos.
3. Edita una receta en un navegador.
4. En el otro navegador deberías ver los cambios automáticamente.

## Si sigue sin funcionar:

Abre la **consola del navegador** (F12) y mira los errores. Te dirán si es un problema de permisos, red o configuración.
