# Sistema de Detección de Placas Vehiculares

## Manual del Usuario Final (Sistema de Detección de Placas)

### Propósito del Sistema
El Sistema de Detección de Placas tiene como objetivo registrar y gestionar incidentes relacionados con vehículos y sus usuarios.

### Guía de Uso para el Operador
1. **Identificación del Vehículo**
   - Captura de Placa.
   - Verificación de Datos.

2. **Registro de una Incidencia**
   - Selección del Operador.
   - Selección del Vehículo.
   - Descripción del Incidente.
   - Evidencia Fotográfica.
   - Envío.

### Consejos para la Solución de Problemas
1. Vehículo no encontrado al capturar la placa.
2. Error al registrar una Incidencia.

---

# Documentación Técnica y Manual de Instalación

## Arquitectura del Sistema
- Cliente Android (Kotlin + TFLite + OCR).
- Backend Django REST.
- IA: YOLOv8 → TFLite + OCR.

## Esquema de la Base de Datos
Modelo que incluye:
- Usuario
- Vehiculo
- Operador
- Incidencia

## Lógica de la Aplicación
El sistema sanciona usuarios con ≥ 3 incidencias mediante señales `post_save`.

## Configuración de API y Comunicación
La constante `BASE_URL` y `network_security_config.xml` permiten tráfico local desde la app hacia el backend.

---

# Manual de Instalación

## Backend
```
pip install Django==5.2.8
pip install djangorestframework==3.16.1
python manage.py makemigrations
python manage.py migrate
python manage.py loaddata fixtures/data.json
python manage.py runserver tuIP:8000
```

## Cliente Android
1. Modificar `BASE_URL` en `Constants.kt`
2. Modificar `network_security_config.xml`
3. Compilar y ejecutar APK
