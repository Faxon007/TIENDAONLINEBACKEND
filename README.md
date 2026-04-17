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


Cumplimiento del proyecto - Requerimientos

Carrito de compras de artículos deportivos
Backend (Node.js)
•
Crear una API REST que permita:
o
Listar productos deportivos (nombre, categoría, precio, stock, imagen).
▪
Las imágenes deben simular estar en S3 usando MinIO o URLs públicas.
▪ 
Incluir lógica para paginación y filtrado por categoría.
o
Agregar productos al carrito.
o
Eliminar productos del carrito.
o
Finalizar la compra (checkout).
▪
Validar disponibilidad de stock.
▪
Registrar la compra en el historial.
▪
Envio de correo de confirmación.
•
Simular funciones Lambda usando serverless-offline.
•
Usar DynamoDB Local para almacenar:
o
Productos disponibles.
o
Carritos de compra por usuario.
o
Historial de compras.
o
Usuarios registrados
•
Implementar autenticación con JWT.
•
Aplicar middleware de autorización para proteger rutas sensibles.
•
Uso de Winston para logging
Frontend (Vue.js o React)
•
Crear una SPA que permita:
o
Ver productos disponibles (con paginación y filtros).
o
Agregar productos al carrito.

