# Selección-Estilo-Arquitectura

* Status: proposed
* Deciders: Nico, Jesus, Ahmad, Natalia, Victor, Arthur
* Date: 2023-10-18

## Context and Problem Statement

Se necesita una arquitectura software para crear un aplicación web de gestión de proyectos que sea capaz de gestionar tareas, usuarios y seguimiento de progreso del proyecto.
En el contexto de nuestro proyecto de desarrollo de software, hemos decidido adoptar una arquitectura de Modelo-Vista-Controlador (MVC) para permitir diferentes vistas de los mismos datos.

## Decision Drivers

* RF1: Migración a Microservicios - Descripción: La compañia debe migrar su arquitectura monolítica a una basada en microservicios. Esto implica dividir las funcionalidades existentes en módulos independientes.
* RF1.1: Protocolo de Acceso a Datos - Descripción: Se requiere sustituir el acceso actual a las dos bases de datos SQL (Clientes, Pedidos) por protocolos HTTP/REST mediante un componente Gateway adecuado.
* RF1.2: La arquitectura existente cuenta con una parte de clientes PC y móvil que acceden a los datos de la emresa alojados en 2 BBDD SQL (Clientes, Pedidos)
* RF2: Módulo de Clientes - Descripción: El módulo de Clientes permite el acceso a los datos personales de los clientes.
* RF3: Módulo de Pedidos - Descripción: El módulo de Pedidos permite a los clientes realizar pedidos de productos a la empresa, con un número limitado de intentos por determinar.
* RF4: Módulo de Reparto y Rutas - Descripción: El módulo de Reparto y Rutas es crítico y gestiona la distribución de flotas de transporte a los clientes y las rutas de camiones, con algoritmos de optimización que se seleccionan en funcion de la demora del camion.
* RF5: Módulo de Estadísticas - Descripción: El módulo de Estadísticas proporciona información en tiempo real sobre los pedidos y la situación de los camiones, incluyendo datos de clientes.
* RF6: Módulo de Incidencias - Descripción: El módulo de Incidencias reporta cualquier tipo de incidencia en las rutas, como camiones averiados o repartos no realizados.
* RF7: Módulo de Pagos - Descripción: El módulo de Pagos actúa como pasarela de pago externa para garantizar la seguridad de los pagos.
* RF8: Componente GestorPedidos - Descripción: El componente GestorPedidos actúa como intermediario entre los módulos de Clientes, Pedidos, Reparto y Incidencias, facilitando la comunicación entre estas funcionalidades.

## Considered Options

* Modelo-Vista-Controlador (MVC)
* Cliente-servidor
* Rest

## Decision Outcome

Chosen option: "Modelo-Vista-Controlador", because La arquitectura de Modelo-Vista-Controlador (MVC) es una forma de organizar el diseño de un sistema software que separa los datos, la lógica y la interfaz de usuario en tres componentes independientes.

### Positive Consequences

* Facilita la migración: MVC facilita la migración de un sistema monolítico a uno basado en microservicios, ya que permite separar la lógica de negocio, la interfaz de usuario y el control del flujo de la aplicación en tres componentes distintos. Esto puede hacer que el código sea más fácil de adaptar y reemplazar.
* Mejora la usabilidad: MVC mejora la usabilidad de la aplicación, ya que permite cambiar la interfaz de usuario sin modificar la lógica de negocio o el controlador. Esto puede resultar en una mejor experiencia para los clientes PC y móvil que acceden a los datos de la empresa.
* Aumenta la cohesión y reduce el acoplamiento: MVC aumenta la cohesión y reduce el acoplamiento entre los componentes de la aplicación, ya que cada uno tiene una responsabilidad clara y definida. Esto puede resultar en un código más limpio y mantenible.

### Negative Consequences

* Requiere más componentes y comunicación: MVC requiere más componentes y comunicación entre ellos que una arquitectura monolítica, ya que los datos deben pasar a través del modelo, la vista y el controlador antes de llegar al usuario. Esto puede afectar al rendimiento y la escalabilidad de la aplicación.
* Puede generar redundancia e inconsistencia: MVC puede generar redundancia e inconsistencia en los datos, ya que cada componente puede tener su propia copia o versión de los datos. Esto puede resultar en problemas de sincronización y actualización de los datos
