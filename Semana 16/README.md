# Restaurante App - Sistema de Gestión - Semana 16

**Nombre:** Diego Narváez


## Proyecto

Esta versión evoluciona el sistema anterior incorporando la gestión completa del módulo de usuarios y productos, implementando controladores basados en eventos, manejo de roles de usuario, atajos de teclado y la separación correcta de responsabilidades entre la interfaz gráfica y la capa de servicios.

## Estructura del Sistema

El proyecto mantiene una arquitectura modular orientada a objetos dividida en datos, modelos, servicios e interfaz gráfica:

```
restaurante_app/
│
├── assets/                  
│   ├── icons/              
│   └── logo/               
│
├── datos/                   
│   ├── productos.json      
│   ├── usuarios.json       
│   └── ventas.json         
│
├── modelos/                 
│   ├── __init__.py
│   ├── producto.py
│   ├── usuario.py
│   └── venta.py            
│
├── servicios/               
│   ├── __init__.py
│   ├── archivo_servicio.py
│   └── restaurante_servicio.py    
│
├── ui/                      
│   ├── __init__.py
│   ├── login_view.py
│   └── main_view.py        
│
├── main.py                  
└── README.md   
```
## Evolución y Características Principales

**Gestión de Usuarios y Productos:** Implementación del CRUD completo (Crear, Consultar, Actualizar y Eliminar) mediante formularios interactivos y componentes `Treeview`.

**Control de Roles:** Incorporación del atributo rol en el modelo de usuario para diferenciar entre **Administrador**, **Empleado** y **Cliente**.

**Seguridad y Acceso:** Restricción de la gestión administrativa exclusivamente para usuarios con rol de **Administrador**.

**Persistencia de Datos:** Almacenamiento seguro y estructurado en archivos locales como `usuarios.json` y bases de datos o servicios dedicados.

**Diseño Visual:** Interfaz clara, coherente y estilizada con uso obligatorio de recursos gráficos, logotipos e iconos ubicados en la carpeta `assets/`.

---

## Uso de Eventos, Bind(), Command y Callbacks

El sistema utiliza una arquitectura basada en eventos para una experiencia de usuario fluida:

**`bind()` y Eventos Virtuales:** Se implementa el evento `<<TreeviewSelect>>` para que al seleccionar una fila en las tablas (tanto de usuarios como de productos), los datos correspondientes se carguen automáticamente en los formularios de edición.

**`command=` en Botones:** Utilizado para la ejecución directa de las acciones principales de los botones como **Registrar**, **Actualizar**, **Eliminar** y **Limpiar**

**Atajos de Teclado:** 

Evento `<Return>` configurado como atajo para confirmar el registro o guardado desde el formulario.

Evento `<Escape>` utilizado para limpiar campos, cancelar selecciones actuales y devolver la interfaz a su estado inicial.

**Combobox:** Integración del evento `<<ComboboxSelected>>` para la selección dinámica de roles.

**Reutilización:** Los callbacks reutilizan la lógica existente en los servicios (`RestauranteServicio`) evitando duplicación de código.

## Requisitos del Sistema

Python 3.10 o superior instalado.

Librerías estándar de Python (`tkinter`, `json`, etc.).

## Pasos para Ejecutar el Proyecto

1. Clona o descarga el repositorio en tu equipo.

2. Abre la carpeta del proyecto en tu entorno de desarrollo (por ejemplo, **PyCharm** o **VS Code**).

3. Asegúrate de que la estructura de carpetas contenga el módulo `assets/` con las imágenes y logos necesarios.

4. Ejecuta el archivo principal desde la terminal o tu IDE

   ```bash
   
   python main.py
