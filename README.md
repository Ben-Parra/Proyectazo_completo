# Proyectazo_completo
Fullstack Evaluacion 3
CONTEXTO:
El proyecto consiste en el desarrollo de una plataforma de gestión clínica basada en arquitectura de microservicios,
orientada a administrar los procesos fundamentales de un centro de salud. 
La problemática abordada corresponde a la necesidad de centralizar y optimizar la gestión de pacientes, 
médicos, citas, historiales clínicos, recetas, pagos y entrega de medicamentos.
La solución implementada utiliza Spring Boot y Spring Cloud para construir servicios independientes
que se comunican entre sí, permitiendo una gestión más escalable, 
mantenible y organizada de la información clínica y administrativa.
------------------------------------------------------------------------------------------------------------------------
CREDITOS:
BENJAMIN PARRA
YOHJAN ROA
ISAIAS SAAVEDRA
------------------------------------------------------------------------------------------------------------------------
ARQUITECTURA:
El sistema está compuesto por una arquitectura de microservicios desarrollada 
con Spring Boot y Spring Cloud, conformada por los siguientes componentes:

Microservicios de Infraestructura:
- Config Server: Centraliza la configuración de todos los microservicios.
- Eureka Server: Permite el registro y descubrimiento de servicios.
- API Gateway: Punto único de entrada para el acceso a los microservicios.

Microservicios de Negocio:
- Pacientes Service: Gestión de pacientes y sus datos personales.
- Médicos Service: Administración de médicos y sus especialidades.
- Medicamentos Service: Gestión del catálogo y stock de medicamentos.
- Citas Service: Administración de citas médicas entre pacientes y médicos.
- Historial Clínico Service: Registro y consulta de historiales clínicos asociados a las citas.
- Recetas Service: Gestión de recetas médicas emitidas a partir de historiales clínicos.
- Pagos Service: Administración de pagos asociados a las atenciones médicas.
- Entrega Medicamentos Service: Registro y control de la entrega de medicamentos según las recetas emitidas.
------------------------------------------------------------------------------------------------------------------------
NETWORKING:

Rutas principales:

pacientes-service            : http://localhost:8090/api/v1/pacientes 
medicos-service              : http://localhost:8090/api/v1/medicos
medicamentos-service         : http://localhost:8090/api/v1/medicamentos
citas-service                : http://localhost:8090/api/v1/citas
historial_clinico-service    : http://localhost:8090/api/v1/historial_clinico
pagos-service                : http://localhost:8090/api/v1/pagos
recetas-service              : http://localhost:8090/api/v1/recetas
entrega_medicamento-service  : http://localhost:8090/api/v1/entrega_medicamento

Endpoints de infraestructura:

API Gateway                  : http://localhost:8090/
Eureka Server                : http://localhost:8999/
Swagger UI Centralizado      : http://localhost:8090/swagger-ui/index.html
------------------------------------------------------------------------------------------------------------------------
ACCESOS:

pacientes-service            : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Pacientes
medicos-service              : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Medicos
medicamentos-service         : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Medicamentos
citas-service                : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Citas
historial_clinico-service    : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Historial-clinico
pagos-service                : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Pagos
recetas-service              : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Recetas
entrega_medicamento-service  : http://localhost:8090/swagger-ui/index.html?urls.primaryName=Entrega-medicamento
------------------------------------------------------------------------------------------------------------------------
GUIA DE DESPLIEGUE:

Entorno Local:

Abrir Xampp y ejecutar Apache junto con MySQL
Ir a la opcion de administrar MySQL, para poder crear las tablas correspondientes, segun el archivo.txt adjunto al proyecto:

CREATE DATABASE IF NOT EXISTS bd_citas;
CREATE DATABASE IF NOT EXISTS bd_entrega_medicamento;
CREATE DATABASE IF NOT EXISTS bd_historial_clinico;
CREATE DATABASE IF NOT EXISTS bd_medicamentos;
CREATE DATABASE IF NOT EXISTS bd_medicos;
CREATE DATABASE IF NOT EXISTS bd_pacientes;
CREATE DATABASE IF NOT EXISTS bd_pagos;
CREATE DATABASE IF NOT EXISTS bd_recetas;

Una vez creadas las tablas, volver a IntelliJ para ejecutar los archivos "Application" en el siguiente orden:
1) ConfigServerApplication : dentro de config-server
2) EurekaServiceApplication : dentro de eureka-service
3) PacientesServiceApplication : dentro de  pacientes-service
4) MedicosServiceApplication : dentro de  medicos-service
5) MedicamentosServiceApplication : dentro de  medicamentos-service
6) CitasServiceApplication : dentro de  citas-service
7) HistorialClinicoServiceApplication : dentro de  historial_clinico-service
8) RecetasServiceApplication : dentro de  recetas-service
9) PagosServiceApplication : dentro de  pagos-service
10) EntregaMedicamentoServiceApplication : dentro de  entrega_medicamento-service
11) ApiGatewayApplication : dentro de api-gateway
12) Visitar cualquiera de los puertos anteriormente adjuntados


Entorno Contenerizado:

Abrir la aplicacion Docker Desktop
Abrir el terminal de IntelliJ, y ejecutar el siguiente comando : docker compose up --build
Esperar a que cargue todas las dependencias
Revisar Docker Desktop, para ver la correcta creacion de los contenedores
Visitar cualquiera de los puertos anteriormente adjuntados


