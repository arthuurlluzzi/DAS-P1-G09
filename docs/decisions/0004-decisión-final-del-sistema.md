# Decisión final del sistema

* Status: proposed
* Deciders: Nico, Jesus, Ahmad, Natalia, Víctor, Arthur
* Date: 2023-11-12

## Context and Problem Statement

Para finalizar la estructura del sistema se ha decidido acabar de especificarlo con un diagrama de paquetes que agrupan las distintas clases del sistema en secciones que se comportan y realizan unas tareas determinadas, distinguiendolas así del resto de la aplicación.
Cabe destacar que la arquitectura final elegida  esta basada en micro-servicios.

## Decision Drivers

* Principalmente se han querido agrupar las clases en paquetes según la funcion que realizan, de ahí que salgan 6 paquetes y una base de datos central
* Algunos paquetes cuentan con similitudes pero se ha decidido no agruparlos en uno solo ya que no cumplen exactamente la misma función, como puede ser el de Información con Clientes y Pedidos.

## Considered Options

* Gestor de pedidos - Cliente
* Gestor de pedidos - Información
* Gestor de pedidos - Rutas
* Gestor de pedidos - Incidencias
* Gestor de pedidos - Pagos
* Pasarela de pagos
* Base de datos

## Decision Outcome

Chosen option: "", because comes out best.
