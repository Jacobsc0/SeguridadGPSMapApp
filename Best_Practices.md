# Best Practices Implementadas en la Aplicación 
## 1. Manejo de Permisos de Ubicación
### Descripción
La aplicación solicita permiso de ubicación de manera clara y directa. Utiliza un diálogo para informar al usuario sobre la necesidad de acceder a su ubicación.
### Mejora en Seguridad
- **Consentimiento del Usuario**: Asegura que los usuarios comprendan por qué se requiere acceso a su ubicación, promoviendo un enfoque transparente y respetuoso.
- **Manejo de Errores**: Implementa una gestión adecuada en caso de que el usuario no otorgue el permiso, evitando comportamientos inesperados de la aplicación.

## 2. Verificación de Permisos
### Descripción
Antes de intentar acceder a la ubicación del dispositivo, la aplicación verifica si el permiso ha sido otorgado.
### Mejora en Seguridad
- **Prevención de Errores**: Al verificar los permisos, la aplicación evita excepciones en tiempo de ejecución que podrían provocar fallos en la misma.

## 3. Gestión de Respuestas de Permiso
### Descripción
La aplicación maneja la respuesta del usuario al solicitar permisos de ubicación y proporciona retroalimentación adecuada si el acceso es denegado.
### Mejora en Seguridad
- **Experiencia del Usuario**: Al informar al usuario sobre la necesidad del permiso y las consecuencias de no otorgarlo, se mejora la experiencia del usuario y se aumenta la probabilidad de que otorgue el acceso.



## 4. Configuración del API Key
### Descripción
El API Key de Google Maps se gestiona de forma segura, almacenándose en un archivo de recursos en lugar de estar codificado directamente en el código fuente.
### Mejora en Seguridad
- **Minimización de Riesgos**: Al evitar la exposición directa de la clave de API en el código, se reduce el riesgo de que sea mal utilizada por terceros.

