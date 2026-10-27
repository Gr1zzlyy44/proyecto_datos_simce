## FUENTES 


| Fuente | Base | Contenido | Años | Formato | Peso | Documentación | ¿Tiene RBD? | Enlace |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :---: | :--- |
| **JUNAEB** | Prioridades con IVE-SINAE | % de vulnerabilidad por colegio | 2010-2023 | .xls | 2,412KB | No encontrada | Sí | [Enlace](https://www.junaeb.cl/ive/) |
| **Agencia de Calidad de la Educación** | SIMCE 4º básico por establecimiento | Puntaje promedio por colegio en Lectura y Matemática, grupo socioeconómico (cod_grupo) y diferencia con el mismo grupo (difgru) | 1988, 2002, 2005–2018, 2022–2024 | .rar | ~5 MB por año | Diccionario de variables (glosas) + Metodología GSE 2012 | Si | [Enlace](https://informacionestadistica.agenciaeducacion.cl/#/bases) |
| **Centro de Estudios Mineduc** | Directorio de establecimientos educacionales | Lista oficial de colegios: comuna, coordenadas, tipos de enseñanza, matrícula, cobros y estado | 1992–2025 | .rar | 914 KB comprimido | Sí | Sí | [Enlace](https://datosabiertos.mineduc.cl/directorio-de-establecimientos-educacionales/) |
| **Centro de Estudios Mineduc** | Asistencia anual por estudiante | En esta sección se encuentran los datos anuales de asistencia por alumno (con MRUN) y trae el grado (COD_GRADO) | 2015-2025 | .rar | 34.3MB Comprimido | Si | Si | [Enlace](https://datosabiertos.mineduc.cl/asistencia-anual-por-estudiante/) |
| **Centro de Estudios Mineduc** | Cargos Docentes | Cada fila es un cargo (un profesor en un colegio). Trae título, tipo de título, especialización, años de servicio, año de titulación, duración de la carrera y modalidad de estudio | 2003–2026 | .rar | 8 MB comprimido | Si | Si | [Enlace](https://datosabiertos.mineduc.cl/cargos-docentes/) |
| Centro de Estudios MINEDUC | Rendimiento por estudiante | Cada fila es un alumno (con MRUN). Trae si aprobó, reprobó o se retiró, y el grado (COD_GRADO) | 2002–2025 | .rar | 41,4 MB comprimido | Sí | Sí | [Enlace](https://datosabiertos.mineduc.cl/rendimiento-por-estudiante-2/) |



## Posibles variables de interés


| Variable | Fuente | Por qué podria importar | 
| :--- | :--- | :--- |
| Pago de matricula y mensualidad | Directorio | El que les cobren mensualidad y matricula podria influir en algo en los resultados |
| Coordenadas | Directorio | Se podria usar para mapear los resultados en power-bi |
| Estado del colegio | Directorio | Para filtrar entre los colegios cerrados o abiertos |
| Años de servicio | Cargos Docentes | Profesores con más experiencia podrían enseñar mejor |
| Tipo de título | Cargos Docentes | Saber si el profesor tiene título en educación o en otra área |
| Modalidad de estudio | Cargos Docentes| Estudiar presencial o a distancia podría reflejar diferencias en la formación |
| Matrícula total | Directorio | El tamaño del colegio podría influir en los resultados |
| Aprobación / reprobación / retiro | Rendimiento | ¿Causa o resultado? Revisar antes de usar en el modelo |

## Observaciones de calidad de datos

En el directorio hay establecimientos que aparecen con matricula total 0 y no aparecen como cerrados.

Se encontró una base de resumen de matriculas por establecimiento pero se descartó ya que no aporta mas que el directorio.

Los archivos de asistencia son tan grandes que excel los corta en 1.048.576 filas, así que hay que leerlos con pandas.

En cargos docentes un mismo profesor puede tener varios cargos y aparecer en varias filas. Hay que tenerlo en cuenta al contar profesores por colegio.

Cargos Docentes no trae la institución donde estudió el profesor.

Rendimiento viene por alumno (igual que asistencia). Para usarlo hay que filtrar 4º básico y resumirlo por colegio.

Los diccionarios del SIMCE no usan nombres consistentes: la hoja de establecimientos se llama _rbd en la mayoría de los años y rbd en 2017 y 2018.