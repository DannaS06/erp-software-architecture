# 1. Introducción y Objetivos

## 1.1 Objetivo del Sistema

El sistema ERP tiene como objetivo integrar y gestionar los procesos administrativos y operativos de la organización en una sola plataforma. 
Permitirá administrar compras, facturación, stock/costos, activos fijos, empleados y reportes ejecutivos (EIS), mejorando el control, trazabilidad y eficiencia de la información.

## 1.2 Objetivos del Módulo de Compras

El módulo de Compras busca:

- Gestionar proveedores.
- Registrar productos.
- Crear y administrar órdenes de compra.
- Registrar entradas de inventario.
- Mantener actualizado el catálogo de productos.
- Garantizar trazabilidad en las adquisiciones.

## 1.3 Requisitos de Negocio Principales

- El sistema debe permitir registrar nuevos productos con nombre, descripción y unidad.
- Debe permitir asociar productos con proveedores.
- Debe permitir registrar órdenes de compra.
- Debe registrar entradas de inventario.
- Debe almacenar la información en una base de datos segura.

---

# 2. Restricciones de Arquitectura

## 2.1 Decisiones Tecnológicas

Para el desarrollo del sistema ERP se definieron las siguientes tecnologías:

- Backend: Java con Spring Boot.
- Frontend: Single Page Application (SPA) desarrollada en React.
- Base de Datos: PostgreSQL.
- Comunicación: API REST mediante HTTPS y formato JSON.
- Control de versiones: GitHub.

## 2.2 Restricciones Técnicas

- La arquitectura será monolítica para simplificar el desarrollo.
- El sistema deberá ejecutarse en un entorno web.
- Se utilizarán estándares REST para la comunicación.

---

# 3. Alcance y Contexto del Sistema

## 3.1 Descripción General

El sistema ERP interactúa con diferentes actores externos como administradores, proveedores y otros sistemas externos. 
Su objetivo es centralizar la gestión de compras y procesos administrativos.

## 3.2 Diagrama de Contexto (C1)

El siguiente diagrama muestra los actores externos que interactúan con el sistema ERP y sus relaciones principales.

![Diagrama de Contexto](./docs/images/Diagrama%20de%20Contexto.png)

---

# 5. Vista de Bloques de Construcción

## 5.1 Diagrama de Contenedores (C2)

El siguiente diagrama muestra los principales contenedores del sistema ERP.

![Diagrama de Contenedores](./docs/images/Diagrama%20de%20Contenedores.png)

## 5.2 Responsabilidad de los Contenedores

### SPA (Frontend - React)
- Interfaz de usuario.
- Permite registrar productos, órdenes y entradas de inventario.
- Se comunica con la API mediante HTTPS/JSON.

### API Monolítica (Spring Boot)
- Maneja la lógica de negocio.
- Valida datos.
- Gestiona reglas del sistema.
- Se conecta a la base de datos.

### Base de Datos (PostgreSQL)
- Almacena productos.
- Almacena proveedores.
- Guarda órdenes de compra.
- Guarda registros de inventario.

---

# 6. Vista de Ejecución

## 6.1 Escenario: Registrar Nuevo Producto

Este escenario describe cómo el gestor registra un nuevo producto en el sistema.

### Flujo:

1. El gestor de inventario completa el formulario en la SPA.
2. La SPA envía los datos a la API mediante una petición POST.
3. La API valida la información.
4. La API inserta los datos en la base de datos.
5. La base de datos confirma la creación.
6. La API responde con estado 201 Created.
7. La SPA muestra mensaje de éxito.

### Diagrama de Secuencia

![Diagrama de Secuencia](./docs/images/Diagrama%20de%20Secuencia.png)

---

# 7. Vista de Despliegue

El sistema ERP se desplegará en un servidor web.

## Arquitectura de Despliegue

- Cliente: Navegador web.
- Servidor de Aplicación: Ejecuta Spring Boot.
- Servidor de Base de Datos: PostgreSQL.
- Comunicación mediante HTTPS.

---

# 10. Glosario

## Producto
Artículo registrado en el sistema con nombre, descripción y unidad de medida.

## Proveedor
Entidad que suministra productos a la organización.

## Orden de Compra
Documento que formaliza la adquisición de productos a un proveedor.

## Entrada de Inventario
Registro que aumenta el stock disponible en el sistema.

## ERP
Sistema de Planificación de Recursos Empresariales que integra procesos administrativos.
