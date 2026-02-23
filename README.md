AgendaPro - Sistema de Gestión de Citas y Servicios

AgendaPro es una aplicación web frontend para la gestión de citas y servicios. Permite a los administradores crear y administrar servicios con horarios y fechas, y a los clientes reservar, reprogramar o cancelar sus citas de forma intuitiva. La aplicación utiliza localStorage para la persistencia de datos, por lo que no requiere backend ni base de datos externa.
Características principales

    Roles de usuario: Administrador, Cliente registrado e Invitado.

    Gestión de servicios (Admin):

        Crear, editar, eliminar y activar/desactivar servicios.

        Configurar fechas disponibles mediante un calendario interactivo.

        Definir horarios (módulos) con capacidad (cupos) por hora.

        Vista previa de imagen y contador de caracteres en descripción.

        Filtros por categoría y estado.

    Panel de administración:

        Visualización de estadísticas (servicios activos, citas próximas, ingresos proyectados).

        Listado de citas con opción de finalizar y contactar por WhatsApp.

        Notificaciones automáticas de nuevas reservas y citas próximas (24h).

    Portal del cliente:

        Explorar servicios activos con filtros por búsqueda y fecha.

        Reservar citas seleccionando fecha y hora disponibles.

        Ver y gestionar reservas propias (cancelar o reprogramar).

        Carrito de reservas con resumen y posibilidad de reagendar (sujeto a restricción de 24h de antelación).

    Reprogramación de citas:

        Los clientes pueden cambiar la fecha/hora de una cita siempre que falten más de 24 horas.

        Validación de disponibilidad en tiempo real.

    Sistema de notificaciones:

        Toast emergente para mensajes informativos, éxito o error.

        Notificaciones internas para el admin sobre nuevas reservas y citas próximas.

    Autenticación simulada:

        Registro e inicio de sesión con almacenamiento local.

        Acceso rápido mediante tokens (ADMIN para admin, cualquier otro para cliente).

        Modo invitado sin necesidad de registro.

Tecnologías utilizadas

    HTML5, CSS3 y JavaScript (ES6+).

    Almacenamiento local del navegador (localStorage).

    Font Awesome para iconos.

    Sin dependencias externas (todo el código JS está incluido en un único archivo).

    Uso
Acceso y roles

    Administrador: En la pantalla de login, haz clic en "Acceso rápido" e ingresa el token ADMIN (o cualquier token que contenga "ADMIN" en mayúsculas). También puedes usar la contraseña predefinida admin123 en el campo correspondiente.

    Cliente registrado: Regístrate con email y contraseña, o inicia sesión si ya tienes una cuenta.

    Invitado: Haz clic en "Continuar como Invitado" en la pantalla de login. Los invitados pueden reservar pero no verán un carrito persistente (se crea un ID de sesión temporal).

Administración

    En admin.html, verás un panel con estadísticas, formulario de creación de servicios y listado de servicios existentes.

    Crear un servicio:

        Completa los campos: nombre, categoría, precio, descripción, imagen.

        Selecciona las fechas en el calendario (puedes usar accesos rápidos como "Solo fines de semana").

        Define los horarios (módulos): hora de inicio, hora de fin y capacidad (cupos). Al agregar un horario, se generarán filas para cada fecha seleccionada, permitiendo ajustar cupos individualmente.

        Marca "Activo" para que el servicio sea visible para los clientes.

    Gestionar servicios: Desde las tarjetas puedes editar, eliminar, activar/desactivar y ver detalles de fechas y horarios.

    Ver citas: La sección "Próximas citas" muestra las reservas con opción a finalizar (marcar como completada) y contactar por WhatsApp. Las notificaciones te alertan de nuevas reservas y citas que ocurrirán en las próximas 24h.

Cliente

    En cliente.html, se listan los servicios activos.

    Filtros: Puedes buscar por nombre o filtrar por fecha específica.

    Reservar:

        Haz clic en "Reservar" en un servicio.

        Selecciona fecha y hora disponibles.

        Completa tus datos (nombre, teléfono, email). Si estás registrado, algunos campos se autocompletan.

        Acepta las condiciones y confirma.

    Mis reservas: En la sección "Mis Reservas" (a la derecha o en el carrito) verás tus citas activas.

        Cancelar: Elimina la cita y libera el cupo.

        Reagendar: Solo disponible si faltan más de 24h para la cita. Te permite elegir nueva fecha/hora entre las disponibles.

    Carrito: Muestra el resumen de tus reservas y el total.

Reprogramación (cliente)

    Desde el carrito, haz clic en "Reagendar" en una cita que cumpla la condición de 24h.

    Se abrirá el mismo modal de reserva, pero con los datos actuales y la opción de seleccionar nueva fecha/hora.

    Al confirmar, la cita original se actualiza y los cupos se reasignan automáticamente.

    /
├── index.html          # Página de login/registro
├── admin.html          # Panel de administración
├── cliente.html        # Portal del cliente
├── script.js           # Todo el código JavaScript
└── README.md           # Este archivo
