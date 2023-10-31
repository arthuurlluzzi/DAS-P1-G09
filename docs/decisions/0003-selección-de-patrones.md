# Selección de Patrones

* Status: proposed
* Deciders: Nico, Jesus, Ahmad, Natalia, Victor, Arthur
* Date: 2023-10-31

## Context and Problem Statement

Tras una reunión de los ASS con los ASC, llegamos a la conclusión de que aplicar varios  patrones de diseño es necesario e esta práctica debido a la complejidad de migrar de una arquitectura monolítica a una basada en microservicios. Estos patrones ayudan a gestionar la adaptación a sistemas heredados, a definir estrategias para módulos críticos como Reparto y Rutas, a proporcionar actualizaciones en tiempo real para Estadísticas, a mediar interacciones entre módulos, a gestionar múltiples tipos de incidencias y a mejorar la claridad y mantenibilidad del código en un entorno en constante evolución. La aplicación adecuada de patrones de diseño facilita la transición y mejora la calidad del sistema resultante.

## Decision Drivers

* Dado que la empresa está migrando de una arquitectura monolítica a una basada en microservicios, es probable que se encuentren diferentes interfaces y protocolos de comunicación entre los módulos. El patrón Adapter se puede usar para adaptar estas interfaces de manera que los microservicios puedan interactuar sin problemas.
* El módulo de Incidencias es responsable de reportar incidencias como camiones averiados o repartos no realizados. El patrón Chain of Reponsability se puede utilizar para construir una cadena de manejadores que procesen diferentes tipos de incidencias de manera jerárquica y flexible. Esto permite un manejo eficiente y personalizable de las incidencias.
* El componente GestorPedidos actúa como intermediario entre varios módulos, como Clientes, Pedidos, Reparto y Incidencias. El patrón Mediador puede ayudar a reducir las dependencias directas entre estos módulos al proporcionar un punto central de comunicación. Esto simplifica la gestión de las interacciones y facilita la expansión del sistema con nuevos módulos en el futuro.
* El módulo de Estadísticas necesita proporcionar información en tiempo real sobre los pedidos y la situación de los camiones. El patrón Observador es útil para notificar a múltiples observadores (como paneles de estadísticas) cuando cambian los datos subyacentes, lo que facilita la actualización en tiempo real de las estadísticas.
* La empresa tiene diferentes módulos con comportamientos variados, algunos críticos y otros no críticos. El patrón Estrategia permite definir una familia de algoritmos, encapsular cada uno de ellos y hacer que sean intercambiables. En este caso, se puede utilizar para gestionar las estrategias de optimización en el módulo de Reparto y Rutas, permitiendo cambiar los algoritmos de optimización según la demora del camión.
* Puede ser valioso para gestionar los estados internos en módulos críticos como el módulo de Reparto y Rutas. El patrón Estado permite que un objeto cambie su comportamiento cuando su estado interno cambia, lo que podría ser relevante para gestionar diferentes estados de camiones, rutas, y situaciones en este módulo complejo.

## Considered Options

* Adapter
* Chain of Responsability
* Mediator
* Observer
* Strategy
* State

## Decision Outcome

Chosen option: "", because comes out best.
