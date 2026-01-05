# Proyecto React + Django REST Framework

Este es un proyecto full-stack que combina React para el frontend y Django con Django REST Framework para el backend.

## Estructura del Proyecto

```
mi_proyecto/
├── api/                 # Aplicación Django para la API
├── backend/             # Configuración principal de Django
├── frontend/            # Aplicación React
│   ├── public/          # Archivos estáticos públicos
│   └── src/             # Código fuente de React
├── manage.py           # Script de administración de Django
└── requirements.txt    # Dependencias de Python
```

## Requisitos Previos

- Python 3.8+
- Node.js 16+
- pip (gestor de paquetes de Python)
- npm (gestor de paquetes de Node.js)

## Instalación

### 1. Configuración del Entorno Virtual (Python)

```bash
# Crear un entorno virtual
python -m venv venv

# Activar el entorno virtual
# En Windows:
.\venv\Scripts\activate
# En macOS/Linux:
source venv/bin/activate
```

### 2. Instalar Dependencias del Backend

```bash
# Instalar dependencias de Python
pip install -r requirements.txt

# Aplicar migraciones
python manage.py migrate

# Crear un superusuario (opcional)
python manage.py createsuperuser
```

### 3. Configuración del Frontend

```bash
# Navegar al directorio del frontend
cd frontend

# Instalar dependencias de Node.js
npm install
```

## Ejecución del Proyecto

### Iniciar el Servidor de Desarrollo de Django (Backend)

```bash
# Asegúrate de estar en el directorio raíz del proyecto
python manage.py runserver
```

### Iniciar el Servidor de Desarrollo de React (Frontend)

```bash
# En una nueva terminal, desde el directorio frontend
cd frontend
npm start
```

El frontend estará disponible en [http://localhost:3000](http://localhost:3000) y el backend en [http://localhost:8000](http://localhost:8000).

## Estructura del Código

### Backend (Django)
- `api/`: Contiene los modelos, serializadores y vistas de la API
  - `models.py`: Modelos de la base de datos
  - `serializers.py`: Serializadores para la API
  - `views.py`: Vistas de la API
  - `urls.py`: Rutas de la API
- `backend/`: Configuración principal de Django
  - `settings.py`: Configuración del proyecto
  - `urls.py`: Rutas principales

### Frontend (React)
- `src/`: Código fuente principal de React
  - `App.js`: Componente principal de la aplicación
  - `index.js`: Punto de entrada de la aplicación
  - `components/`: Componentes reutilizables
  - `services/`: Lógica para consumir la API

## Configuración de CORS

El proyecto ya incluye `django-cors-headers` configurado para permitir peticiones desde el frontend. La configuración se encuentra en `backend/settings.py`.

## Despliegue

Para desplegar el proyecto en producción, asegúrate de:

1. Configurar `DEBUG = False` en `backend/settings.py`
2. Configurar `ALLOWED_HOSTS` con tu dominio
3. Configurar una base de datos en producción
4. Configurar archivos estáticos con `python manage.py collectstatic`
5. Usar un servidor WSGI como Gunicorn o uWSGI

## Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.
