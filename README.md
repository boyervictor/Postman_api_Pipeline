# Postman_api_Pipeline

Proyecto educativo de automatización de pruebas de APIs REST utilizando **Postman**, **Newman** y **GitHub Actions** para ejecutar las pruebas como parte de un flujo de **CI/CD** simple.

---

## 📌 Objetivo

Demostrar cómo crear, automatizar y ejecutar pruebas básicas de una API REST pública usando Postman y luego integrarlas con un pipeline automatizado en GitHub Actions.

---

## 🚀 Tecnologías utilizadas

- [Postman](https://www.postman.com/)
- [Newman](https://www.npmjs.com/package/newman)
- [GitHub Actions](https://docs.github.com/en/actions)
- API pública: [JSONPlaceholder](https://jsonplaceholder.typicode.com)

---

## 🧪 Casos de prueba incluidos

La colección incluye pruebas automatizadas para los siguientes endpoints de `https://jsonplaceholder.typicode.com/users`:

| Método | Descripción              |
|--------|--------------------------|
| GET    | Obtener usuarios         |
| POST   | Crear nuevo usuario      |
| PUT    | Actualizar usuario (ID 1)|
| DELETE | Eliminar usuario (ID 1)  |

---

## 🛠 Estructura del proyecto

Postman_api_Pipeline/
├── collections/
│ └── api-tests.postman_collection.json
├── environment/
│ └── dev.postman_environment.json (opcional)
├── .github/
│ └── workflows/
│ └── postman-ci.yml


---

## ⚙️ CI/CD con GitHub Actions

El archivo `postman-ci.yml` ejecuta automáticamente las pruebas de la colección cada vez que se hace `push` o `pull request` en la rama `main`.

```yaml
# Resumen del pipeline:
- Instala Node.js
- Instala Newman
- Ejecuta la colección de Postman

