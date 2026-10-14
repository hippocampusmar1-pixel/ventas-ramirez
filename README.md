# Ventas Ramírez para Android

Este proyecto convierte el archivo HTML de Ventas Ramírez en una aplicación Android con WebView. Incluye el HTML de la versión que se adjuntó a la conversación y adapta los accesos de mapas para Android/Google Maps.

## Funciones del contenedor Android

- Ejecuta la aplicación localmente desde los recursos incluidos en el APK.
- Habilita JavaScript y almacenamiento local persistente en el WebView.
- Solicita permiso de ubicación solo cuando se usa la función GPS.
- Abre enlaces de WhatsApp y de Google Maps en las aplicaciones compatibles del teléfono.
- Permite seleccionar archivos para restaurar respaldos o cargar fotos de productos.
- Convierte las descargas CSV/JSON en un selector nativo para guardar el archivo.
- Envía la opción de imprimir a la función de impresión de Android.

## Crear el APK usando GitHub Actions

El entorno donde se preparó este paquete no tiene instalado el Android SDK y no tiene acceso de red para descargarlo; por eso este archivo ZIP contiene el proyecto listo para compilar y el flujo automatizado, no un APK ya compilado.

1. Descomprime el ZIP.
2. Crea un repositorio nuevo en GitHub y sube al repositorio **el contenido** de esta carpeta, incluida la carpeta oculta `.github`.
3. Asegúrate de que la rama principal se llame `main`. Al subir el proyecto, se ejecutará el flujo **Compilar APK Ventas Ramírez**; también puedes abrir la pestaña **Actions** y ejecutarlo manualmente.
4. Abre la ejecución cuando termine y descarga el artefacto **Ventas-Ramirez-APK**.
5. Descomprime el artefacto descargado. El archivo instalable se llama `app-debug.apk`.
6. Envía `app-debug.apk` a tu teléfono Android, ábrelo desde Descargas y autoriza la instalación para la aplicación desde donde lo abriste, si Android lo solicita.

La compilación es de prueba/debug, apta para instalar directamente para uso personal. No es una versión de publicación firmada para Google Play.

## Cómo pasar tus datos al Android

Los datos que tengas en Safari, Chrome u otro navegador **no se copian automáticamente** a la app Android, ya que el almacenamiento es independiente.

1. En la versión que ya usas, entra a **Más → Respaldo de datos → Exportar respaldo** y guarda el archivo JSON.
2. Abre Ventas Ramírez en Android.
3. Entra a **Más → Restaurar respaldo seleccionado**, selecciona ese JSON y confirma la restauración.
4. Revisa productos, clientes, ventas y saldos antes de continuar trabajando.

Conserva una copia del JSON fuera del teléfono. Restaurar un respaldo reemplaza los datos actuales de esa instalación.

## Requisitos y notas

- Android 6.0 (API 23) o posterior.
- La información se guarda localmente en el almacenamiento privado de la app. Desinstalarla o borrar sus datos puede eliminarla; usa respaldos periódicos.
- GPS requiere permiso de ubicación. Google Maps, WhatsApp, los enlaces externos y la navegación necesitan internet y/o las aplicaciones correspondientes.
- No se ha podido probar este proyecto en un dispositivo Android real desde el entorno de preparación; revisa el flujo de venta, el guardado y la exportación/restauración después de instalarlo.

## Construcción local en Android Studio

Abre la carpeta como proyecto Gradle en Android Studio con conexión a internet para que descargue Android Gradle Plugin y dependencias. Configura SDK Platform 35 y ejecuta la tarea **app → Tasks → build → assembleDebug**. El archivo se genera en `app/build/outputs/apk/debug/app-debug.apk`.
