# Actualización Estilo Arquitectura

* Status: proposed
* Deciders: Nico, Jesus, Ahmad, Natalia, Victor, Arthur
* Date: 2023-10-29

## Context and Problem Statement

Durante esta semana hemos estado revisando e intentando ampliar la información ya existente sobre la arquitectura y los requisitos del sistema a idear. Hemos visto que la arquitectura seleccionada era demasiado general y no estaba enfocado a la aplicación que necesita el cliente.

## Decision Drivers

* Al diseñar los distintos diagramas nos hemos dado cuenta que al tener como arquitectura principal Modelo Vista Controlador no podemos seguir una estructura determinada que nos ayude a simplificar y enlazar todos los servicios con los que cuenta el sistema.
* Tanto los diseños como los requisitos nos estaban indicando que el modelo elegido no era el adecuado.

## Considered Options

* Arquitectura-de-Microservicios
* Arquitectura-de-Eventos
* Modelo-Vista-Controlador
* Cliente-Servidor
* Rest

## Decision Outcome

Chosen option: "Arquitectura-de-Microservicios", because se trata de una arquitectura más específica que explica con más detalle como funcionará el sistema y soluciona nuestros problemas de diseño ya que simplifica el modo en el que interactuan las distintas funciones entre sí.

### Positive Consequences

* Escalabilidad: Los microservicios permiten escalar cada servicio de manera independiente, lo que facilita la gestión de la carga y la mejora del rendimiento de partes específicas de la aplicación.
* Desarrollo paralelo: Se puede trabajar en mejoras y correcciones de forma simultánea ya que los servicios son independientes
* Tecnología diversa: Cada microservicio puede estar construido con diferentes tecnologías y lenguajes, lo que permite utilizar la tecnología más adecuada para cada tarea.
* Mayor estabilidad: Si existe un fallo en uno de los módulos el resto del sistema sigue funcionando, ya que son independientes

### Negative Consequences

* Complejidad: La gestión de múltiples microservicios puede ser compleja, ya que se requiere coordinación entre ellos y una infraestructura sólida para gestionar la comunicación.
* Requiere un cambio de mentalidad en el equipo de desarrollo: Adoptar la arquitectura de microservicios a menudo requiere un cambio en la organización, así como nuevas prácticas de desarrollo y operaciones.
* Latencia: La comunicación entre microservicios a través de la red puede aumentar la latencia, lo que resulta en un problema en el tiempo de respuesta.