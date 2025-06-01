# Secure Software Development Life Cycle (SDLC)

## 1. Requisitos de Seguridad
- Validación de entrada desde el frontend.
- Aislamiento del entorno gracias a Docker.
- Separación de entornos entre desarrollo y producción.
- Uso de librerías oficiales y actualizadas.

## 2. Diseño Seguro
- Arquitectura cliente-servidor.
- Docker expone solo el puerto necesario (3000).
- Variables sensibles se manejarían mediante `.env` (si se usaran credenciales).

## 3. Implementación Segura
- Código mantenido bajo control de versiones.
- Escaneo de dependencias (`npm audit`).
- Eliminación de archivos innecesarios del contenedor.

## 4. Pruebas de Seguridad
- Auditoría de dependencias con `npm audit`.
- Test unitarios mediante `jest`.

## 5. Despliegue Seguro
- Contenedores limitados a lo mínimo.
- Imagen basada en `node:18-alpine` (liviana y segura).
- Ningún puerto innecesario expuesto.

## 6. Mantenimiento
- Control de versiones con Git.
- Posibilidad de integración con `dependabot` o CI/CD para futuras auditorías.

---
