# Descripción del proyecto
Desarrollo de un API REST para gestionar un recurso de tareas. La API permite crear, leer, actualizar y eliminar tareas, utilizando únicamente una lista en memoria como persistencia. 

# Instrucciones de instalación 
Configuración inicial: 
1. Clonar el repositorio:
git clone https://github.com/GustHernandez/Desarrollo-web-meta-3.1.git

2. Instalar dependencias:
npm install

3. Instalar Express: 
npm install express

4. Intala nodemon como dependencia de desarrollo: 
npm install --save-dev nodemon

5. Ejecutar el servidor:
npm run dev

# Lista de endpoints disponibles
| Método | Endpoint          | Descripción                        | Body (JSON)                                           |
| ------ | ----------------- | ---------------------------------- | ----------------------------------------------------- |
| GET    | `/api/tareas`     | Obtener todas las tareas           | -                                                     |
| GET    | `/api/tareas/:id` | Obtener una tarea por ID           | -                                                     |
| POST   | `/api/tareas`     | Crear una nueva tarea              | `{"titulo": "Nueva tarea", "completada": false}`      |
| PUT    | `/api/tareas/:id` | Actualizar completamente una tarea | `{"titulo": "Tarea actualizada", "completada": true}` |
| PATCH  | `/api/tareas/:id` | Actualizar parcialmente una tarea  | `{"completada": true}`                                |
| DELETE | `/api/tareas/:id` | Eliminar una tarea                 | -                                                     |
| GET    | `/api/tareas/buscar?q=texto`| Buscar tareas por titulo |                                                      | 

# Capturas de pantalla de las pruebas en Postman
![Prueba en Thunder Client usando GET](images/GET-api-tareas.png)

![Prueba en Thunder Client usando POST](images/POST-api-tareas.png)

![Prueba en Thunder Client usando PUT](images/PUT-api-tareas-1.png)

![Prueba en Thunder Client usando PATCH](images/PATCH-api-tareas-1.png)

![Prueba en Thunder Client usando GET](images/GET-api-tareas-buscar.png)

![Prueba en Thunder Client usando GET](images/GET-api-tareas-formato-text.png)

# Estructura MVC
El proyecto sigue el patrón de arquitectura MVC (Modelo-Vista-Controlador):
- **Modelo:** Representa la estructura de los datos. En este proyecto las tareas se almacenan en una lista en memoria. 
- **Controlador:** Contiene la lógica que maneja las solicitudes HTTP y manipula las tareas. 
- **Rutas:** Definen los endpoints disponibles y conectan las peticiones con los controladores. 

# Diferencia entre PUT y PATCH
- **PUT:** Actualiza completamente un recurso. Se debe enviar el objeto completo, ya que reemplaza todos los datos existentes. 
- **PATCH:** Actualiza solo una parte del recurso. Solo se envían los campos que se desean modificar.

# Estado HTTP utilizados
- **200 OK:** La solicitud se procesó correctamente.
- **201 Created:** Se creó un nuevo recurso al crear una tarea.
- **400 Bad Request:** La solicitud tiene datos inválidos.
- **404 Not Found:**  No se encontró la tarea solicitada.
- **500 Internal Server Error:** Error interno del servidor.