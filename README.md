# 💧 Control de Producción de Agua Purificada

Aplicación web móvil para el control y seguimiento de la producción de botellones de agua purificada.

## 🚀 Características

- **Interfaz móvil optimizada**: Diseño responsivo pensado para dispositivos móviles
- **Registro de producción**: Permite registrar la cantidad de botellones producidos por fecha
- **Consultas y estadísticas**: Visualización de producción por día, mes o rango de fechas
- **Base de datos en la nube**: Integración con Supabase para almacenamiento persistente
- **Fallback local**: Funciona con localStorage si no hay conexión a Supabase
- **Tiempo real**: Resumen actualizado de la producción del día actual

## 📱 Funcionalidades

### Registro de Producción
- Registro de botellones producidos por fecha
- Resumen en tiempo real de la producción del día
- Historial de los últimos 5 registros
- Validación de datos de entrada

### Consultas y Reportes
- Producción del día actual
- Producción del mes actual
- Consulta por rango de fechas personalizado
- Estadísticas: total, promedio diario, días registrados
- Lista detallada de producción por fecha

## 🛠️ Tecnologías Utilizadas

- **HTML5**: Estructura de la aplicación
- **CSS3**: Diseño responsivo con gradientes y animaciones
- **JavaScript ES6+**: Lógica de la aplicación
- **Supabase**: Base de datos PostgreSQL en la nube
- **LocalStorage**: Almacenamiento local de respaldo

## ⚙️ Configuración

### 1. Configurar Supabase

1. Crea una cuenta en [Supabase](https://supabase.com)
2. Crea un nuevo proyecto
3. Ve a la sección SQL Editor y ejecuta el siguiente script:

```sql
CREATE TABLE produccion_agua (
    id BIGSERIAL PRIMARY KEY,
    botellones INTEGER NOT NULL,
    fecha DATE NOT NULL,
    timestamp TIMESTAMPTZ DEFAULT NOW(),
    created_at TIMESTAMPTZ DEFAULT NOW()
);

-- Habilitar Row Level Security (opcional pero recomendado)
ALTER TABLE produccion_agua ENABLE ROW LEVEL SECURITY;

-- Política para permitir todas las operaciones
CREATE POLICY "Permitir todas las operaciones" ON produccion_agua
FOR ALL USING (true);
```

### 2. Configurar Credenciales

En el archivo `index.html`, actualiza las siguientes variables con tus credenciales de Supabase:

```javascript
const SUPABASE_URL = 'TU_SUPABASE_URL';
const SUPABASE_ANON_KEY = 'TU_SUPABASE_ANON_KEY';
```

### 3. Ejecutar la Aplicación

Simplemente abre el archivo `index.html` en tu navegador web o despliega en Vercel.

## 📊 Estructura de Datos

La tabla `produccion_agua` tiene la siguiente estructura:

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | BIGSERIAL | Identificador único (clave primaria) |
| botellones | INTEGER | Cantidad de botellones producidos |
| fecha | DATE | Fecha de producción |
| timestamp | TIMESTAMPTZ | Marca de tiempo del registro |
| created_at | TIMESTAMPTZ | Fecha de creación del registro |

## 🎨 Diseño

- **Colores principales**: Azul (#2196F3) y gradientes
- **Tipografía**: Arial, sans-serif
- **Iconos**: Emojis para mejor UX
- **Animaciones**: Transiciones suaves y efectos hover
- **Responsive**: Optimizado para móviles y tablets

## 🔧 Funcionalidades Técnicas

- **Manejo de errores**: Fallback automático a localStorage
- **Validación de datos**: Verificación de entrada del usuario
- **Ordenamiento**: Datos ordenados por fecha descendente
- **Agrupación**: Suma automática de producciones por fecha
- **Navegación**: Interfaz de pestañas intuitiva

## 📱 Uso

1. **Registrar Producción**:
   - Ingresa la cantidad de botellones
   - Selecciona la fecha (por defecto es hoy)
   - Presiona "Registrar Producción"

2. **Consultar Datos**:
   - Ve a la pestaña "Consultas"
   - Selecciona el tipo de consulta deseada
   - Para rangos personalizados, selecciona fechas de inicio y fin

## 🚀 Características Avanzadas

- **Persistencia dual**: Supabase + localStorage
- **Tiempo real**: Actualización automática de estadísticas
- **Interfaz intuitiva**: Diseño centrado en la experiencia del usuario
- **Validaciones robustas**: Prevención de errores de entrada
- **Responsive design**: Funciona en cualquier dispositivo

## 📄 Licencia

Este proyecto está bajo la Licencia MIT.

## 👨‍💻 Autor

Desarrollado por [csubi1974](https://github.com/csubi1974)

---

**¡Perfecto para pequeñas y medianas empresas de agua purificada que necesitan un control simple y efectivo de su producción!** 💧