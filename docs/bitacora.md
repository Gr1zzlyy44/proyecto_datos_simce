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