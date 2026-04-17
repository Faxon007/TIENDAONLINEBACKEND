# TIENDAONLINEBACKEND
# Ecommerce Serverless API

## Requisitos

* Node.js
* (Opcional) Docker

---

## Ejecutar proyecto

```bash
npm install
npx serverless offline
```

---

## Modo por defecto se hizo al inicio pero se cambio a Dynamo( paso 1) (sin dependencias externas, este ya no se termino) 

El proyecto funciona en memoria:

```env
DB_MODE=memory
```

No requiere configuración adicional.

---

## Modo DynamoDB Local (opcional)

### 1. Levantar DynamoDB

```bash
docker run -p 8000:8000 amazon/dynamodb-local
```

### 2. Crear tablas

```bash
node scripts/createTables.js
```

### 3. Insertar datos

```bash
node scripts/seedDynamo.js
```

### 4. Cambiar modo

```env
DB_MODE=dynamo
```

---

## Endpoints

* POST /login
* GET /products
* POST /cart
* GET /cart
* POST /checkout
* GET /orders

---

## Notas

El proyecto estaba pensado soporta dos modos de persistencia, pero por cuestiones de tiempo se dejo solo el Dynamo:

* Memoria (rápido para pruebas) 
* DynamoDB Local (simulación AWS)

