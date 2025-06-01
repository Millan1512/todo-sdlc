Todo SDLC App
Aplicación de ejemplo desarrollada como parte del módulo de Metodología de Desarrollo Seguro. Esta aplicación consiste en una API sencilla construida con Node.js y Express, ejecutándose dentro de contenedores Docker para facilitar el aislamiento, despliegue y seguridad.

Cómo ejecutar la aplicación
Clona o descomprime el repositorio.

Asegúrate de tener Docker instalado y funcionando.

Abre una terminal en la carpeta todo-sdlc.

Ejecuta:

bash
Copiar
Editar
docker compose up --build
Esto levantará el contenedor que contiene la API escuchando en el puerto 3000.

Consideraciones de seguridad aplicadas
Durante el diseño y despliegue de esta aplicación, se han aplicado las siguientes medidas de seguridad:

Aislamiento del entorno usando contenedores Docker.

Exposición controlada de puertos (solo el puerto 3000).

Uso de imagen base segura: node:18-alpine.

Escaneo de vulnerabilidades en dependencias con npm audit.

Separación de scripts de desarrollo (nodemon) y producción (start).

Eliminación de archivos sensibles del contenedor final.

Ejecución en entorno non-root por defecto en Alpine.

Documentación de seguridad en seguridad/SDLC.md.

Auditoría de seguridad guardada en:

bash
Copiar
Editar
seguridad/auditorias/npm-audit.json
Paso a paso: Construcción siguiendo el S-SDLC
Fase 1: Requisitos de seguridad
Aislamiento del entorno de ejecución.

Validación de entradas planificada.

Identificación de dependencias externas para su análisis.

Fase 2: Diseño
Arquitectura cliente-servidor minimalista.

Selección de imagen base segura (node:alpine).

Contenedor con exposición de un solo puerto.

Fase 3: Implementación
Instalación limpia de paquetes con npm install.

Definición del script start en package.json.

Dockerfile estructurado en múltiples capas.

Separación del entorno de desarrollo y producción.

Fase 4: Verificación y pruebas
Auditoría con npm audit guardada en seguridad/auditorias/.

Verificación en entorno aislado mediante contenedores Docker.

Fase 5: Despliegue
Uso de docker-compose para orquestar servicios.

Contenedor auto-contenido y listo para producción.

Fase 6: Mantenimiento
Documentación técnica y de seguridad.

Proyecto preparado para integración con Dependabot o CI (GitHub Actions).

Fácil actualización de dependencias y despliegue automatizado.

Aplicación del enfoque DevSecOps
Esta aplicación sigue una mentalidad DevSecOps desde su planteamiento. La integración de seguridad no es un paso aislado, sino parte del flujo completo de desarrollo:

Desarrollo: Se emplean buenas prácticas de codificación, validación mínima de entrada y dependencias reducidas.

Integración continua: Aunque no se ha implementado un pipeline, el proyecto está preparado para integrarse con GitHub Actions, Dependabot y herramientas de auditoría automatizada.

Despliegue continuo: El uso de Docker y docker-compose permite un despliegue uniforme y seguro en cualquier entorno.

