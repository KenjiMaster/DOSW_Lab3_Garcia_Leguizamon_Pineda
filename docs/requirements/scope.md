# 📄 Requerimientos del Sistema

## 1. Sistema

* Nombre del sistema: TechCup
* Objetivo: El sistema tiene como objetivo: Permitir la creación de torneos de fútbol y la gestión del registro y pago de inscripción de los equipos participantes de los progamas de la Escuela.

## 2. Problema a resolver
Actualmente la Escuela no cuenta con un sistema centralizado para crear torneos, registrar equipos, procesar y validar pagos, ni generar reportes hacia la Decanatura, lo que hace el proceso manual, lento y propenso a errores.

## 3. Diagrama de Contexto

### 3.1 Diagrama

![Imagen Diagrama de contexto](../uml/Diagrama%20de%20Contexto%20TechCup.png)

### 3.2 Actores

| Actor / Rol                        |          Descripción              |
|------------------------------------|:---------------------------------:|
| Estudiante                      | Usuario que se autentica en la plataforma  |
| Capitán del equipo        |  Usuario que crea el equipo, realiza el pago y lo inscribe a un torneo              |
| Organizador  | Usuario de administra torneos, valida pagos, aprueva registros y genera reportes  |
| Decanatura   | Recibe los reportes de pago de la inscripcion |

### 3.3 Sistemas externos

| Sistema                            |                                    Descripción                                        |
|------------------------------------|:-------------------------------------------------------------------------------------:|
| PSE                         | Pasarela de pago externa que procesa el pago de un equipo    |

## 4. Alcance del sistema

### 4.1 Dentro del sistema
* El sistema permite a los organizadores crear un torneo, cambiar su estado y modificar su información.
* El sistema permite a los capitanes crear equipos, registrar sus miembros, modificar la información del equipo y realizar el pago de inscripción.
* El sistema permite a los organizadores consultar y verificar los pagos realizados por los equipos.
* El sistema permite a los organizadores aprobar las inscripciones de los equipos.
* El sistema permite generar reportes de los equipos inscritos y de los ingresos obtenidos por concepto de inscripción.
* El sistema permite el inicio de sesión de organizadores y estudiantes.
### 4.2 Fuera del sistema
* El sistema no permite tener más de un torneo activo simultáneamente.
* El sistema no cuenta con soporte técnico.
* El sistema no permite tener un torneo con más de un día de duración.
