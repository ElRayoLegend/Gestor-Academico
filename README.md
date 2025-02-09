# Gestor Académico - 2023147

## Laboratorio # 2

### Descripción

El proyecto consiste en una aplicación de ambiente web (solo Backend) para la administración del control de alumnos en un centro educativo. La aplicación se desarrollará utilizando las tecnologías siguientes:

- **Node.js**
- **MongoDB**
- **Express**

Además, se utilizarán las siguientes librerías adicionales:

- **Bcrypt**
- **Mongoose**
- **JWT**

El sistema contará con dos roles: **TEACHER_ROLE** y **STUDENT_ROLE**, donde el registro y las funciones serán diferentes para cada uno.

---

## Funciones del Alumno

El **Alumno** podrá realizar las siguientes acciones:

1. **Registrarse** como `STUDENT_ROLE` por defecto y loguearse.
2. **Asignarse a un máximo de 3 cursos**.
3. **No podrá asignarse** a un curso que ya tenga alumnos asignados.
4. **Visualizar los cursos** a los que está asignado.
5. **Editar y eliminar su perfil**.

---

## Funciones del Maestro

El **Maestro** podrá realizar las siguientes acciones:

1. **Registrarse** como `TEACHER_ROLE` y loguearse.
2. **Crear, editar, eliminar y visualizar los cursos** que posea.
3. Si un **maestro edita un curso** con alumnos asignados, estos deberán ser actualizados automáticamente con los cambios del curso.
4. Si un **maestro elimina un curso** con alumnos asignados, los alumnos serán desasignados automáticamente del curso.

---

## Aspectos a Tener en Cuenta

1. **Funcionalidad**: El sistema debe cumplir con todas las funcionalidades descritas.
2. **Autodidacta**: El desarrollo debe ser realizado de manera autónoma, investigando y utilizando las herramientas necesarias.
3. **Cumplimiento de Instrucciones**: Es esencial seguir las instrucciones y requerimientos establecidos en este documento.
4. **Validaciones Implícitas**: Se deben aplicar las validaciones necesarias, como la verificación de roles y la validación de asignaciones de cursos, entre otras.

---

## Tecnologías Utilizadas

- **Node.js**: Entorno de ejecución para el desarrollo del servidor.
- **MongoDB**: Base de datos NoSQL para almacenar la información.
- **Express**: Framework de Node.js para facilitar el desarrollo del backend.
- **Bcrypt**: Librería para el hash de contraseñas.
- **Mongoose**: Librería para interactuar con MongoDB en Node.js.
- **JWT (JSON Web Token)**: Para la gestión de autenticación y autorización.

---

## SOLICITUDES POSTMAN

**REGISTER STUDENT**
**URL:** `/api/auth/registerStudent`
**Metodo:** `POST`
**Cuerpo:**
````json
    {
        "name": "string",
        "surname": "string",
        "username": "string",
        "password": "string",
        "email": "email",
        "phone": "string",
        "role": "ROLE",
        "profilePicture": "file"
    }
````

**REGISTER TEACHER**
**URL:** `/api/auth/registerTeacher`
**Metodo:** `POST`
**Cuerpo:**
````json
    {
        "name": "string",
        "surname": "string",
        "username": "string",
        "password": "string",
        "email": "email",
        "phone": "string",
        "role": "ROLE",
        "profilePicture": "file"
    }
````

**LOGIN STUDENT**
**URL:** `/api/auth/login`
**Metodo:** `POST`
**Cuerpo:**
````json
    {
        "email": "email",
        "password": "string"
    }
````

**LIST STUDENTS**
**URL:** `/api/student/`
**Metodo:** `GET`

**LIST STUDENT BY ID**
**URL:** `/api/student/:id`
**Metodo:** `GET`

**DELETE STUDENT**
**URL:** `/api/student/deleteStudent/:id`
**Metodo:** `DELETE`

**UPDATE PASSWORD**
**URL:** `/api/student/updatePassword/:id`
**Metodo:** `PATCH`
**Cuerpo:**
````json
    {
        "newPassword": "string"
    }
````

**ASSIGN COURSE**
**URL:** `/api/student/enrollInCourse`
**Metodo:** `POST`
**Cuerpo:**
````json
    {
        "studentId": "id",
        "courseId": "id"
    }
````

**LIST STUDENT COURSES**
**URL:** `/api/student/getCourses/:id`
**Metodo:** `GET`

**UPDATE STUDENT**
**URL:** `/api/student/updateStudent/:id`
**Metodo:** `PUT`
**Cuerpo:**
````json
    {
        "name": "string",
        "surname": "string",
        "username": "string",
        "password": "string",
        "email": "email",
        "phone": "string",
        "role": "ROLE",
        "profilePicture": "file"
    }
````
**LIST TEACHERS**
**URL:** `/api/teacher/`
**Metodo:** `GET`

**LIST TEACHER BY ID**
**URL:** `/api/teacher/findTeacher/:id`
**Metodo:** `GET`

**DELETE TEACHER**
**URL:** `/api/teacher/deleteTeacher/:id`
**Metodo:** `DELETE`

**UPDATE PASSWORD TEACHER**
**URL:** `/api/teacher/updatePassword/:id`
**Metodo:** `PATCH`
**Cuerpo:**
````json
    {
        "newPassword": "string"
    }
````

**ADD COURSE**
**URL:** `/api/teacher/addCourse`
**Metodo:** `POST`
**Cuerpo:**
````json
    {
        "name": "string",
        "teacherId": "id"
    }
````

**UPDATE COURSE**
**URL:** `/api/teacher/updateCourse/:id`
**Metodo:** `PUT`
**Cuerpo:**
````json
    {
        "name": "string"
    }
````

**DELETE COURSE**
**URL:** `/api/teacher/deleteCourse/:id`
**Metodo:** `DELETE`

**LIST TEACHER COURSES**
**URL:** `/api/teacher/getCourses/:id`
**Metodo:** `GET`

**LIST ALL COURSES**
**URL:** `/api/course/`
**Metodo:** `GET`