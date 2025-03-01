# MySQL desde Cero

## 📌 1. Conceptos Básicos
- **MySQL** es un sistema de gestión de bases de datos relacional (RDBMS).
- Se usa **SQL** (Structured Query Language) para interactuar con las bases de datos.
- Puedes manejar MySQL con:
  - **MySQL Workbench** (Interfaz gráfica).
  - **Bash** (Línea de comandos con `mysql`).

## 📌 2. Instalación y Acceso en Bash
- Abre la terminal y accede a MySQL con:
  ```bash
  mysql -u root -p
  ```
- Introduce la contraseña del usuario `root`.

## 📌 3. CRUD en MySQL
CRUD se refiere a las cuatro operaciones principales en bases de datos:

### ✅ CREATE (Insertar Datos)
- Crear una base de datos:
  ```sql
  CREATE DATABASE tienda;
  ```
- Usar la base de datos:
  ```sql
  USE tienda;
  ```
- Crear una tabla:
  ```sql
  CREATE TABLE productos (
      id INT AUTO_INCREMENT PRIMARY KEY,
      nombre VARCHAR(100),
      precio DECIMAL(10,2),
      stock INT
  );
  ```
- Insertar datos en la tabla:
  ```sql
  INSERT INTO productos (nombre, precio, stock)
  VALUES ('Laptop', 1200.50, 10);
  ```

### 🔍 READ (Consultar Datos)
- Ver todas las bases de datos:
  ```sql
  SHOW DATABASES;
  ```
- Ver todas las tablas:
  ```sql
  SHOW TABLES;
  ```
- Obtener todos los productos:
  ```sql
  SELECT * FROM productos;
  ```
- Filtrar productos con precio mayor a 500:
  ```sql
  SELECT * FROM productos WHERE precio > 500;
  ```

### ✏️ UPDATE (Actualizar Datos)
- Modificar el precio de un producto:
  ```sql
  UPDATE productos SET precio = 1100 WHERE id = 1;
  ```

### ❌ DELETE (Eliminar Datos)
- Borrar un producto específico:
  ```sql
  DELETE FROM productos WHERE id = 1;
  ```
- Vaciar la tabla (elimina todos los datos pero deja la estructura):
  ```sql
  TRUNCATE TABLE productos;
  ```
- Borrar la tabla completamente:
  ```sql
  DROP TABLE productos;
  ```

## 📌 4. Manejo Visual con MySQL Workbench
1. **Abrir MySQL Workbench** y conectarte a la base de datos.
2. **Crear una Base de Datos** en la pestaña "Schemas".
3. **Crear Tablas** usando el botón derecho y seleccionando "Create Table".
4. **Insertar Datos** con la opción "Insert Rows".
5. **Ejecutar Queries** en la pestaña "Query" escribiendo SQL y presionando `Ctrl + Enter`.

## 📌 5. Bash y MySQL
Si quieres ejecutar SQL desde **Bash**, usa:
```bash
mysql -u root -p -e "SHOW DATABASES;"
```
Para importar un archivo SQL:
```bash
mysql -u root -p tienda < backup.sql
```
Para exportar datos:
```bash
mysqldump -u root -p tienda > backup.sql
```

---
📚 **¡Practica y prueba estos comandos en tu entorno MySQL!** 🚀
