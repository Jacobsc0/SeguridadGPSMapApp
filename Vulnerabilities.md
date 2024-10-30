# Vulnerabilities Report

## Summary
- Total vulnerabilities found: 5
- Critical: 0
- High: 2
- Medium: 0
- Low: 3

## Detailed Findings

### 1. Uso de Versiones Antiguas de Android
- **Description**: La aplicación está presente en versiones de Android antiguas (Android 8.1, API nivel 27) que presentan múltiples vulnerabilidades conocidas y ya no reciben actualizaciones de seguridad.
- **Severity**: Low
- **Impact**: Potencial exposición a vulnerabilidades ya conocidas en versiones antiguas.
- **Steps to Reproduce**: Verificar el nivel de API configurado en el archivo de manifiesto.
- **Remediation**: Aumentar la compatibilidad mínima a Android 10 (API nivel 29) o superior para mejorar la seguridad.

### 2. Depuración Habilitada en la Aplicación
- **Description**: La depuración está habilitada en la aplicación (android:debuggable=true), lo que facilita el trabajo de ingeniería inversa al permitir que los atacantes conecten un depurador para acceder a la traza de pila y clases de ayuda de depuración.
- **Severity**: High
- **Impact**: Permite el acceso no autorizado y facilita la ingeniería inversa.
- **Steps to Reproduce**: Revisar el archivo de manifiesto para verificar la propiedad `android:debuggable`.
- **Remediation**: Deshabilitar la depuración en versiones de producción.

### 3. Protección de Permisos en el Broadcast Receiver
- **Description**: El receptor ProfileInstallReceiver tiene la propiedad `android:exported=true`, lo que lo hace accesible a otras aplicaciones. Aunque está protegido por el permiso `android.permission.DUMP`, la aplicación no define este permiso, por lo que se debe revisar su nivel de protección.
- **Severity**: Low
- **Impact**: Una aplicación maliciosa podría obtener el permiso y acceder al componente.
- **Steps to Reproduce**: Revisar la configuración de permisos en el archivo AndroidManifest.xml.
- **Remediation**: Configurar el permiso como `signature` si el acceso debe limitarse a aplicaciones firmadas con el mismo certificado, o cambiar `android:exported` a `false` si no es necesario que otras aplicaciones accedan a este componente.

### 4. Permitir Copia de Seguridad de los Datos de la Aplicación
- **Description**: La opción `allowBackup` está habilitada, permitiendo que usuarios con depuración habilitada copien datos.
- **Severity**: Low
- **Impact**: Posibilidad de extracción de datos sensibles mediante herramientas de copia de seguridad.
- **Steps to Reproduce**: Revisar el archivo AndroidManifest.xml para la configuración de `allowBackup`.
- **Remediation**: Configurar `android:allowBackup="false"` en el archivo AndroidManifest.xml.

### 5. Exposición de Información Sensible a Través de Permisos
- **Description**: La aplicación solicita permisos sensibles como `ACCESS_FINE_LOCATION` y `ACCESS_COARSE_LOCATION`, lo que puede ser utilizado por aplicaciones maliciosas para rastrear la ubicación del usuario sin su consentimiento.
- **Severity**: High
- **Impact**: Posible rastreo de la ubicación del usuario sin consentimiento.
- **Steps to Reproduce**: Revisar los permisos solicitados en el archivo AndroidManifest.xml.
- **Remediation**: Evaluar la necesidad de estos permisos y establecer un mecanismo de consentimiento claro y explícito para los usuarios.
