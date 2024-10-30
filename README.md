# SimpleGPSMapApp #

# Descripción 
Este proyecto es una aplicación Android que implementa medidas de seguridad para proteger contra vulnerabilidades comunes. 

## Vulnerabilidades Identificadas 
- Uso de versiones antiguas de Android (API nivel 27) con vulnerabilidades conocidas.
- Depuración habilitada en la aplicación (android:debuggable=true).
- Protección de permisos insuficiente en el Broadcast Receiver.
- Copia de seguridad permitida, lo que expone datos sensibles (android:allowBackup=true).
- Exposición de información sensible a través de permisos de ubicación (ACCESS_FINE_LOCATION y ACCESS_COARSE_LOCATION).

## Mejoras Implementadas 
- Aumento de la compatibilidad mínima a Android 10 (API nivel 29) para mejorar la seguridad.
- Deshabilitación de la depuración en versiones de producción.
- Configuración de permisos estrictos en el Broadcast Receiver (`android:exported=false` o permisos `signature`).
- Deshabilitación de la opción de copia de seguridad de datos (`android:allowBackup="false"`).
- Revisión de los permisos de ubicación para limitar la exposición de información sensible y establecer un mecanismo de consentimiento claro para los usuarios.

## Documentación 
- [Vulnerabilidades](vulnerabilities.md) 
- [Best Practices](best_practices.md) 
- [Security Tips](security_tips.md) 
- [Security Improvement Program](security_improvement_program.md) 
- [Reporte de Vulnerabilidades](vulnerability_report.pdf)

## Cómo Ejecutar la Aplicación de Forma Segura 
1. Clonar el repositorio.
2. Importar el proyecto en Android Studio.
3. Asegurarse de que los permisos necesarios están configurados.
4. Ejecutar la aplicación en un dispositivo o emulador configurado en un entorno seguro.
5. Revisar el archivo `vulnerability_report.pdf` para obtener información detallada sobre las vulnerabilidades detectadas y las recomendaciones de seguridad.

## Resumen del Reporte de Vulnerabilidades
El reporte detallado de las pruebas de vulnerabilidad realizadas se encuentra en el archivo `vulnerability_report.pdf`.
