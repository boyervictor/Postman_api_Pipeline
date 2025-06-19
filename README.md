# Postman API Pipeline

![CI](https://github.com/boyervictor/Postman_api_Pipeline/actions/workflows/postman-ci.yml/badge.svg)

Este proyecto educativo demuestra cómo automatizar pruebas de una API REST utilizando Postman, Newman y GitHub Actions en un flujo CI/CD simple.

---

## 📦 Contenido

La colección incluye pruebas automatizadas para los siguientes endpoints de [https://jsonplaceholder.typicode.com/users](https://jsonplaceholder.typicode.com/users):

- **GET**: Listar usuarios
- **POST**: Crear nuevo usuario
- **PUT**: Actualizar usuario existente
- **DELETE**: Eliminar usuario

---

## 🧪 Tecnologías utilizadas

- [Postman](https://www.postman.com/) – Para definir y ejecutar las pruebas.
- [Newman](https://www.npmjs.com/package/newman) – Para ejecutar las colecciones desde la terminal o CI.
- [GitHub Actions](https://docs.github.com/en/actions) – Para integrar las pruebas en un flujo de integración continua.

---

## ⚙️ Estructura del repositorio

├── .github/
│ └── workflows/
│ └── postman-ci.yml # Workflow que ejecuta Newman en cada push/pull request
├── collections/
│ └── api-tests.postman_collection.json # Colección con pruebas GET, POST, PUT, DELETE
├── README.md


---

## 🚀 Cómo se ejecutan las pruebas

Cada vez que haces `push` o un `pull request` hacia la rama `main`, GitHub Actions ejecuta automáticamente el workflow definido en `.github/workflows/postman-ci.yml`.  
Este workflow:

1. Instala Node.js
2. Instala Newman globalmente
3. Ejecuta las pruebas con la colección `collections/api-tests.postman_collection.json`
4. Genera un reporte HTML (`newman-report.html`)

---

## 📄 Ejemplo de ejecución (CLI)

```bash
newman run collections/api-tests.postman_collection.json --reporters cli,html --reporter-html-export newman-report.html
