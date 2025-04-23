# encode-product-api

**encode-product-api** es una API RESTful desarrollada en .NET 8. Permite gestionar productos mediante operaciones CRUD (Create, Read, Update, Delete) y está construida siguiendo una **arquitectura en capas**, aplicando los principios de **Clean Code** y **SOLID** para garantizar escalabilidad, mantenibilidad y claridad en el código.

---

## 🛠️ Tecnologías utilizadas

- ASP.NET Core
- Entity Framework Core
- SQLite
- Swagger (OpenAPI)
- Postman (colección para pruebas)

---

## 📐 Arquitectura del proyecto

El proyecto está organizado en capas, respetando el principio de separación de responsabilidades:
```
/ProductApi 
├── Controllers → Manejo de las peticiones HTTP
├── Context → Configuración del DbContext y base de datos
├── Interfaces → Contratos que definen el comportamiento de los servicios
├── Models → Entidades del dominio (como Product)
├── Services → Implementación de la lógica de negocio
└── Program.cs → Configuración general y punto de entrada
``` 

---

## ✅ Requisitos previos

- .NET SDK 7 o superior
- IDE recomendado: Visual Studio
- Postman (opcional, para pruebas)

---

## 🚀 Ejecutar la API localmente

1. Clonar el repositorio

```bash
git clone https://github.com/Fermoyano07/encode-product-api.git
cd encode-product-api
```

2. Restaurar paquetes

```bash
dotnet restore
```

3. Aplicar migraciones y crear la base de datos SQLite

```bash
dotnet ef database update
```

> Si no tenés las herramientas de EF Core:
```bash
dotnet tool install --global dotnet-ef
```

4. Ejecutar la API

```bash
dotnet run
```

### La API estará disponible en:
- https://localhost:7033  
- Swagger UI: https://localhost:7033/swagger

---

## 📌 Endpoints principales

| Método | Ruta                     | Descripción              |
|--------|--------------------------|--------------------------|
| GET    | `/api/Products`         | Obtener todos los productos |
| GET    | `/api/Products/{id}`    | Obtener un producto por ID |
| POST   | `/api/Products`         | Crear un nuevo producto     |
| PUT    | `/api/Products/{id}`    | Actualizar un producto      |
| DELETE | `/api/Products/{id}`    | Eliminar un producto        |

---

## 🧪 Pruebas con Postman

Se incluye una colección de Postman para probar los endpoints de la API.

### Importar la colección

1. Abrir Postman  
2. Clic en **Importar**  
3. Seleccionar el archivo `Postman/test-encode-api.postman_collection.json` incluido en este repositorio  
4. Ejecutar las peticiones contra `https://localhost:7033`

---

## 💾 Base de datos

Se utiliza **SQLite**. El archivo `Products.db` se genera automáticamente si no existe.

La cadena de conexión está en `appsettings.json`:

```json
"ConnectionStrings": {
  "AppConnection": "Data Source=Products.db"
}
```

---

## 👤 Autor

**Fernando Moyano**  
[GitHub](https://github.com/Fermoyano07)
