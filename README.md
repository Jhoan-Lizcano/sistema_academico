# sistema_academico
Base de datos de un sistema académico tipo universitario

# 🎓 credicel_jhoan — Base de Datos Académica Universitaria

> 💡 Proyecto académico desarrollado en **MySQL Workbench**, que modela la estructura de información de una institución educativa: estudiantes, docentes, programas académicos, asignaturas e inscripciones.  
> Incluye relaciones completas, vistas, procedimientos almacenados y datos de prueba realistas (más de 2000 estudiantes y 130 docentes).

---

## 📘 Descripción general

Esta base de datos fue creada como proyecto final para representar el funcionamiento interno de un **sistema académico universitario**, cubriendo los procesos de:

- Registro de **estudiantes** y **docentes**  
- Administración de **programas académicos** (carreras)  
- Asignación de **asignaturas** a cada programa  
- Vinculación de **docentes** a las asignaturas que dictan  
- **Matrícula de estudiantes** en las asignaturas correspondientes  

El diseño busca mantener una estructura **limpia, normalizada y con integridad referencial**, cumpliendo las reglas de normalización hasta 3FN.

---

## 🧱 Estructura principal

| Tabla | Descripción | Tipo de relación |
|-------|--------------|------------------|
| **programa_academico** | Contiene los programas o carreras (Psicología, Ingeniería, Derecho, etc.) | 1 : N con `estudiante` |
| **asignatura** | Lista de todas las materias de los programas | N : M con `programa_academico` |
| **estudiante** | Información personal y académica de los estudiantes | N : M con `asignatura` |
| **docente** | Información de los docentes (nombres, género, nacionalidad, etc.) | N : M con `asignatura` |
| **programa_asignatura** | Tabla intermedia entre programas y asignaturas | N : M |
| **docente_asignatura** | Tabla intermedia entre docentes y asignaturas | N : M |
| **inscripcion** | Registro de qué estudiantes cursan cada asignatura | N : M |

---

## 🔗 Diagrama Entidad–Relación (ERD)

![Diagrama ERD](docs/ERD.png)

*(Puedes ver el diagrama completo en la carpeta `/docs` del repositorio.)*

---

## 📊 Vistas incluidas

| Vista | Descripción |
|--------|-------------|
| **vista_estudiantes_asignaturas_detalle** | Muestra cada estudiante con las asignaturas en las que está matriculado y su cantidad total. |
| **vista_docente_asignaturas** | Lista cada docente junto con las asignaturas que dicta. |
| **vista_asignatura_docentes** | Muestra las asignaturas y qué docentes las imparten. |
| **vista_resumen_docentes** | Resumen general de los docentes y el número de asignaturas que dictan. |

---

## ⚙️ Cómo restaurar la base de datos

### 🔸 Opción 1 — MySQL Workbench
1. Abre `Server → Data Import`.  
2. Selecciona **Import from Self-Contained File**.  
3. Carga el archivo:  
