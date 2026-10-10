## 2026-10-07 — Problemas con DBeaver

**Contexto:** Instalacion de DBeaver

**Problema:** Al querer ejecutar DBeaver una vez instalado arrojo el error Failed to find a Main Class in `C:\Program Files\DBeaver\\plugins/org.jkiss.dbeaver.launcher_1.0.62.202610041844.jar`

**Causa:** Pasó porque en el momento de la instalacion no le puse el ticket que decia "Include Java" y "Add Microsoft Defender Antivirus Exclusion" 

**Solución:** Reinstalar el DBeaver y dejar marcados ambos ticket

**Aprendizaje:** Trataria de averiguar antes de usar un programa el proceso correcto de instalacion.

## 2026-10-07 — Problemas instalacion postgreSQL

**Contexto:**  Estaba instalando postgreSQL 

**Problema:** El instalador nunca me pidio la clave de admin por lo cual no podia conectarme con DBeaver

**Causa:** Tenia varias teorias en el momento pero la causa real era que ya habia un directorio existente de una vez anterior en la cual se instaló postgreSQL por lo cual utilizo esos datos 

**Solución:** Para solucionar el problema tuve que desinstalar el ultimo postgres instalado y borrar la carpeta ya existente y reinstalar todo desde 0 sin datos antiguos

**Aprendizaje:** Aprendi a que al momento de instalar o desinstalar un programa verificar que no queden datos pendientes de instalaciones o desinstalaciones anteriores

## 2026-10-08 — No versionar los datos

**Contexto:** Configurando el repo me di cuenta que si subia todos los datos utilizados en el proyecto se haria pesado y lento. Tambien se pensó que con el tiempo los datos irian cambiando por lo cual si algun usuario utilizara el script podria usar los datos acorde a su periodo

**Decisión:** Se decidio no subir los datos usados en el proyecto

**Razones:** Los datos pesas bastante y al subirlos al repositorio con el pasar del tiempo se volveria pesado y lento. Tambien cabe agregar que los datos son publivod (Cualquier los puede descargar de la fuente original) y los procesados se generan con los scripts

**Alternativas consideradas:** Subir los datos tal cual. Git LFS sirve para guardar archivos pesados en Github, pero tiene limite gratis y complica a quien clona el repo. Subir una muestra chica que podria servir para mas adelante para pruebas.

**Consecuencias:** El no versionar los datos produce un repo mas ligero pero tambien podria generar discrepancias en los resultados obtenidos por mi y por un usuario que utilice el script en otro momento. Las personas que quieran utilizar los scripts con los mismos datos deberan ir y descargarlos desde los sitios oficiales. Para evitar esto al descargar cada archivo se anotará su fecha, enlace y hash.