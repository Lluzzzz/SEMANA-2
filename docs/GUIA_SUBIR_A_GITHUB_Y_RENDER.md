# Cómo publicar BIOPRINT-VASC Semana 2 — Guía paso a paso

Este proyecto usa **Python + SQLite**. GitHub almacena el código, pero **GitHub Pages NO ejecuta las rutas `/api/` ni SQLite**. Para compartir un enlace interactivo necesitas un hosting para Python, como Render.

## 1. Probar en tu computadora

1. Descarga y extrae el ZIP; abre la carpeta que contiene `app.py` y `render.yaml`.
2. Instala Python 3 si todavía no lo tienes.
3. En Windows, ejecuta `INICIAR_WINDOWS.bat`. O abre una terminal dentro de esa carpeta y ejecuta `python app.py`.
4. Abre `http://127.0.0.1:8000/`.
5. En la portada, desplaza el control **Separación entre canales** y compara 0.30 mm contra 0.80 mm.
6. Ejecuta los módulos, guarda una prueba en SQLite y luego abre **Historial**.

## 2. Subir a GitHub

1. Entra en tu repositorio de la semana 1 desde https://github.com y guarda un respaldo si quieres conservar su versión.
2. Elige **Add file → Upload files**.
3. Arrastra **el contenido de la carpeta descomprimida**, no únicamente el archivo ZIP, ni una carpeta contenedora adicional. Deben quedar `app.py`, `numericos.py`, `index.html`, `render.yaml` y `src/` en la raíz del proyecto.
4. En el commit escribe `Semana 2 - visualizador de tejidos y cálculos` y confirma. Revisa que aparezcan `src/oxygen_model.js` y `src/visual.js`.
5. No subas `data/*.sqlite3`, `__pycache__`, `.env` ni archivos de contraseñas: `.gitignore` ya los excluye para subidas con Git, pero si usas la web evita arrastrarlos manualmente.

## 3. Generar un enlace público con Render

1. Ve a https://dashboard.render.com y entra con tu cuenta.
2. Pulsa **New → Blueprint**; conecta tu repositorio en GitHub y autoriza el acceso necesario.
3. Selecciona el repositorio que contiene `render.yaml` en su raíz. Render reconocerá un **Web Service de Python**.
4. Inicia el despliegue. Cuando Render marque el servicio como listo, copia la dirección `https://NOMBRE.onrender.com` que te asigne.
5. Comprueba `https://NOMBRE.onrender.com/api/health`. Debe responder con `"ok": true`.
6. Después abre la dirección principal, desliza el control del tejido, ejecuta una simulación y guarda un experimento.
7. Si Render dice `app.py not found`, corrige el **Root Directory** para que apunte a la carpeta que contiene `app.py`.

Alternativa manual: **New → Web Service**, entorno Python, Build Command `python -m compileall -q app.py numericos.py`, Start Command `python app.py` y Health Check `/api/health`.

**Almacenamiento:** Render gratuito tiene un sistema de archivos temporal. SQLite puede funcionar mientras el servicio esté activo, pero perder datos al reiniciar, suspenderse o redesplegarse. Para historial verdaderamente persistente necesitas un almacenamiento duradero compatible (por ejemplo un disco persistente en un servicio de pago) y configurar `BIOPRINT_DB_PATH` apuntando a ese volumen. La prueba de SQLite local sí conserva datos en disco.

## 4. Qué enlace enviar en Classroom

Adjunta: (i) enlace al **repositorio GitHub** actualizado; (ii) enlace público real de **Render** para ejecutar el proyecto; (iii) `docs/Informe_Experimentos_Semana2_UMSA.pdf` como informe.

**Nunca** entregues `http://127.0.0.1:8000/` como enlace público: solo funciona en tu computadora. Si la web se abre desde GitHub Pages, es una vista estática y no permitirá ejecutar `/api/simulate`, `/api/save` ni `/api/history`.
