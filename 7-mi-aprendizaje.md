# Mi aprendizaje
Antes de realizar esta práctica, tenía una comprensión general de Docker como herramienta de contenedores, pero no dominaba la estructura ni el propósito de un Dockerfile. Las políticas de reinicio eran conceptos que conocía superficialmente, sin haberlas aplicado en un entorno real. También tenía dudas sobre cómo se construyen imágenes, cómo se gestionan versiones, y cómo Docker maneja el almacenamiento y el mapeo de puertos.

---
Ahora puedo comprender de mejor manera los siguientes temas:
### Dominio del Dockerfile

- Comprendí la función de cada instrucción (`FROM`, `RUN`, `COPY`, `CMD`, `ENTRYPOINT`, `EXPOSE`, `ENV`, `VOLUME`) y cómo se traduce en capas dentro de la imagen.
- Aprendí a construir imágenes con `docker build -t nombre:tag .` y a usar nombres personalizados para Dockerfiles con `-f`.

### Gestión de versiones y caché

- Observé cómo Docker reutiliza capas mediante su mecanismo de caché, lo que optimiza el tiempo de construcción.
- Aprendí a modificar archivos como `index.html` y reconstruir imágenes con nuevas versiones (por ejemplo, `apache-samira:2.0`).

### Mapeo de puertos y ejecución de contenedores

- Entendí cómo mapear puertos del contenedor al host con `-p`, y cómo verificar el mapeo con `docker ps`.
- Pude acceder a mi aplicación web desde el navegador usando `localhost:8080`.

### Políticas de reinicio

- Probé las políticas `no`, `always`, `unless-stopped` y `on-failure`, observando cómo se comportan ante detención manual o reinicio del demonio Docker.
- Aprendí a usar `--restart` y a verificar el comportamiento con `docker ps -a`.

### Limpieza y mantenimiento

- Identifiqué imágenes huérfanas con `docker images -f "dangling=true"` y las eliminé con `docker image prune`, manteniendo mi entorno limpio.

---

## 🛠️ Problema solucionado

Al intentar ejecutar `mi-apache:1.0`, recibí el error: *docker: Error response from daemon: pull access denied for mi-apache, repository does not exist...*
Detecté que la imagen no existía localmente. Verifiqué con `docker images` y confirmé que el nombre correcto era `apache-samira:1.0`. Ejecuté el contenedor con ese nombre y funcionó correctamente.


