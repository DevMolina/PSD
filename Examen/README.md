# Examen: Programación de sistemas Digitales

## Descripción
Se necesita desarrollar un sistema de gestión de parqueaderos. El sistema permitirá registrar vehículos, gestionar espacios de parqueo y realizar cobros.  

---

## Ejercicio 1: Registro de Vehículos (Diccionarios y Manejo de Datos)  
Implemente una función `registrar_vehiculo()` que almacene los vehículos en un diccionario con la siguiente estructura:

```python
{
    "ABC123": {"tipo": "Carro", "propietario": "Juan Pérez"},
    "XYZ789": {"tipo": "Moto", "propietario": "María Gómez"}
}
```

- La función debe permitir agregar un nuevo vehículo solicitando la placa, tipo y nombre del propietario.  
- Si la placa ya está registrada, debe mostrar un mensaje de error.  
- Retornar el diccionario actualizado después de cada registro.  

### **Ejemplo de uso:**
```python
registrar_vehiculo("LMN456", "Carro", "Carlos Díaz")
```
**Salida esperada:**
```
Vehículo con placa LMN456 registrado exitosamente.
```

---

## Ejercicio 2: Asignación de Espacios de Parqueo (Listas y Ciclos)  
Implemente una función `asignar_espacio()` que asigne un espacio a un vehículo.

- El parqueadero tiene **10 espacios numerados del 1 al 10**.
- Un vehículo solo puede ocupar un espacio libre.
- Si el parqueadero está lleno, debe mostrar un mensaje de error.
- La función debe devolver el estado actual del parqueadero.

### **Ejemplo de interacción:**
```
Asignando espacio a vehículo con placa XYZ789...
Espacio 3 asignado.
```

**Estado del parqueadero:**
```python
{1: None, 2: None, 3: "XYZ789", 4: None, ..., 10: None}
```

---

## Ejercicio 3: Control de Excepciones en el Registro de Ingresos y Salidas  
Implemente una función `registrar_ingreso_salida()` que reciba la placa del vehículo y registre la hora de ingreso o salida.

- Si el vehículo no está registrado, debe lanzar una excepción personalizada.
- Si el vehículo ya está dentro del parqueadero, debe registrar su salida y calcular el tiempo de permanencia.
- Si el vehículo no está dentro del parqueadero, debe registrar su ingreso con la hora actual.

### **Ejemplo de uso:**
```python
registrar_ingreso_salida("ABC123")
```
**Salida esperada:**
```
Vehículo ABC123 ingresó a las 14:30.
```
Luego, al ejecutar nuevamente:
```
Vehículo ABC123 salió. Tiempo total: 2 horas.
```

---

## Ejercicio 4: Cálculo de Tarifas y Generación de Reportes  
Cree una función `calcular_tarifa()` que reciba la placa de un vehículo y determine el costo del parqueo con base en la siguiente tarifa:

- **Carro:** $5000 por hora  
- **Moto:** $3000 por hora  

- La función debe leer el tiempo de permanencia del vehículo y calcular el total a pagar.
- También debe generar un **reporte en JSON** con el historial de pagos.

### **Ejemplo de salida:**
```json
{
    "ABC123": {"tiempo": 2, "total": 10000},
    "XYZ789": {"tiempo": 3, "total": 9000}
}
```
---
## Ejercicio 5: API Flask para Consulta de Parqueo  
Implemente una API Flask con los siguientes endpoints:

- `GET /parqueadero` → Devuelve el estado actual del parqueadero.
- `POST /ingresar` → Recibe una placa y asigna un espacio si hay disponibilidad.
- `POST /salir` → Recibe una placa y libera el espacio ocupado, registrando la salida.
- `GET /vehiculo/<placa>` → Devuelve la información de un vehículo registrado.
- `GET /tarifa/<placa>` → Devuelve la información de un vehículo registrado.

### **Ejemplo de respuesta para `GET /parqueadero` cuando hay dos vehículos:**
```json
{
    "1": "ABC123",
    "2": null,
    "3": "XYZ789",
    "4": null,
    "5": null,
    "6": null,
    "7": null,
    "8": null,
    "9": null,
    "10": null
}
```