# Sistema de Parqueadero

## Descripción General

Anteriormente se trabajo en un sistema de parqueadero funcional en consola, ahora se requiere llevarlo a un nivel más avanzado, transformándolo en un **sistema completo y profesional**, incluyendo persistencia de datos, posibilidad de integración web y **su implementación física real**.

---

## Objetivo

Desarrollar un sistema de **gestión de parqueadero** que permita:

- Registrar vehículos
- Asignar espacios
- Calcular tarifas
- Generar reportes históricos
- Proponer cómo funcionaría realmente el sistema en un entorno físico

El sistema deberá incluir almacenamiento en una base de datos y ofrecer una API REST o interfaz web que permita su uso y administración eficiente. Además, deberá contener una propuesta técnica para su instalación real: entradas, sensores, hardware, red, etc.

---

## Fases del Desarrollo

### Fase 1: Modelado de Base de Datos

- Diseñar un esquema de base de datos que represente:
  - Vehículos registrados
  - Espacios del parqueadero
  - Historial de ingresos y salidas
- Entregar el **Diagrama Entidad-Relación** 

---

### Fase 2: Persistencia

- Conectar el sistema con una base de datos real:
  - `SQLite` o 
  - `PostgreSQL` o
  - `MySQL` 
- Usar un ORM como `SQLAlchemy` para mapear las clases a la base de datos.
- Reemplazar los diccionarios temporales por tablas en la base de datos.

---

### Fase 3: API REST

- Crear una API con mínimo los siguientes endpoints:
  - `POST /vehiculos` → Registrar vehículos
  - `POST /parqueadero/asignar` → Asignar espacio
  - `POST /vehiculo/ingreso` y `POST /vehiculo/salida` → Registrar entrada/salida
  - `GET /historial/{placa}` → Consultar historial de un vehículo
- Framework sugerido: `Flask`.

---

### Fase 4: Propuesta de Implementación Física

Proponer cómo el sistema podría usarse en **la vida real**. Incluir:

- **Diseño de distribución del parqueadero**: Entradas, salidas, zonas de parqueo.
- **Sensores y automatización**:
  - ¿Qué sensores usarían para detectar un vehículo?
  - ¿Se usarían cámaras, tags RFID, lector de placas, barreras automáticas?
- **Punto de control / cabina**:
  - ¿Dónde estaría el operador?
  - ¿Cómo visualiza el sistema?
- **Interacción físico-digital**:
  - ¿Qué datos llegan del mundo físico al sistema?
  - ¿Qué decisiones puede tomar automáticamente?
- **Conectividad y red**:
  - ¿Qué tecnología de red usarían?
  - ¿Es un sistema local o alojado en la nube?
- **Energía**: ¿Dónde irían los dispositivos? ¿Qué fuente de alimentación necesitan?

Entregable: Un documento corto (PDF) con:
- Plano esquemático del parqueadero (puede ser hecho a mano o con herramientas digitales)
- Lista de componentes electrónicos sugeridos
- Flujo de funcionamiento entre el hardware y el software

---

### Fase 5: Interfaz Web o Funcionalidades Extra

- Crear una interfaz gráfica con HTML/CSS/JS o un framework como React.
- Agregar funcionalidades adicionales como:
  - Login de usuarios (administrador, operador)
  - Tarifas personalizadas
  - Reportes exportables (PDF o Excel)
  - Sistema de reservas anticipadas

---

## Entregables

1. **Código fuente completo** (preferiblemente en GitHub)
2. **Script SQL** para crear la base de datos o archivo `.db` (si usan SQLite)
3. **Manual de uso** (puede ser documento o video demostrativo)
4. **PDF con el modelo de base de datos**
5. **Propuesta de implementación física (documento)**
6. **Documentación técnica de la API (Swagger, Postman u otra)**

---

## Extras (para puntos adicionales)

- Frontend web funcional (interfaz)
- Reportes en PDF o Excel
- Sistema de login y roles
- Documentación técnica de la API
- Simulación de hardware con Arduino, ESP32 u otros

---

## Recomendaciones

- Comenzar por el diseño de base de datos
- Mantener un control de versiones del proyecto
- Repartir tareas entre integrantes
- No duden en solicitar apoyo técnico si se quedan bloqueados

---
