## 1. Uso de Versiones Antiguas de Android
- **Severidad**: Advertencia
- **Descripción**: La aplicación se está presente en versiones de Android antiguas (Android 8.1, API nivel 27) que presentan múltiples vulnerabilidades conocidas y ya no reciben actualizaciones de seguridad.
- **Recomendación**: Aumentar la compatibilidad mínima a Android 10 (API nivel 29) o superior para mejorar la seguridad.

## 2. Depuración Habilitada en la Aplicación
- **Severidad**: Alta
- **Descripción**: La depuración está habilitada en la aplicación (android:debuggable=true), lo que facilita el trabajo de ingeniería inversa al permitir que los atacantes conecten un depurador para acceder a la traza de pila y clases de ayuda de depuración.
- **Recomendación**: Deshabilitar la depuración en versiones de producción para evitar accesos no autorizados.

## 3. Protección de Permisos en el Broadcast Receiver
- **Severidad**: Advertencia
- **Descripción**: El receptor ProfileInstallReceiver tiene la propiedad android:exported=true, lo que lo hace accesible a otras aplicaciones. Aunque está protegido por el permiso android.permission.DUMP, la aplicación no define este permiso, por lo que se debe revisar su nivel de protección. Si el permiso está configurado como normal o dangerous, una aplicación maliciosa podría obtener el permiso y acceder al componente.
- **Recomendación**: Configurar el permiso como signature si el acceso debe limitarse a aplicaciones firmadas con el mismo certificado, o cambiar android:exported a false si no es necesario que otras aplicaciones accedan a este componente. Actualiza AndroidManifest.xml según la configuración requerida:

## 4.Permitir Copia de Seguridad de los Datos de la Aplicación
- **Severidad**: Advertencia
- **Descripción**: La opción allowBackup está habilitada, permitiendo que usuarios con depuración habilitada copien datos.
- **Recomendación**: Configurar android:allowBackup="false" en el archivo AndroidManifest.xml:


## 5. Exposición de Información Sensible a Través de Permisos
- **Severidad**: Alta
- **Descripción**: La aplicación solicita permisos sensibles como ACCESS_FINE_LOCATION y ACCESS_COARSE_LOCATION, lo que puede ser utilizado por aplicaciones maliciosas para rastrear la ubicación del usuario sin su consentimiento.
- **Recomendación**: Evaluar la necesidad de estos permisos y utilizar métodos alternativos de localización o establecer un mecanismo de consentimiento claro y explícito para los usuarios.

