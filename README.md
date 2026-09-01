# Bitácora del error 

| Campo | Contenido |
|---|---|
| **Síntoma** | `WipError -32000 Cannot find context with specified id`, repetido en llamadas del AppInspector y al intentar hot reload (`r`). |
| **Causa identificada** | Refresqué de manera manual la pestaña de Chrome en lugar de utilizar el comando (`r`) en la consola. Dicha situación causó un nuevo `ContextId`, mientras que la app seguía usando el contexto anterior, el cual ya no existía. Como resultado, aunque la pestaña seguía corriendo, la terminal ya no podía comunicarse con ella. |
| **Solución aplicada** | Primero intenté probar con `Shift + R` desde la terminal, pero como el contexto era otro, no resolvía el problema. Luego utilicé la opción `q` para detener la sesión por completo y volví a correr `flutter run` para iniciar una conexión nueva con la comunicación correcta entre la consola y la pestaña de Chrome. |
| **Verificación** | Al volver a correr `flutter run` dejaron de aparecer los errores en la consola y la app mostró nuevamente la pestaña actualizada, dado que la conexión se restauró por completo. |

# verificacion_entorno

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

