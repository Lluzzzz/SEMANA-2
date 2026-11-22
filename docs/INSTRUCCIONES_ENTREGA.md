# Qué entregar a Classroom en Semana 2

El documento oficial exige **tres evidencias principales**:

1. **Enlace funcional de BIOPRINT-VASC Semana 2** alojado con ejecución de Python y almacenamiento SQLite persistente. La aplicación local en `http://127.0.0.1:8000/` funciona para la defensa en tu computadora, pero no es un enlace público que pueda abrir el docente desde la suya. **GitHub Pages solo no puede ejecutar `app.py`.** No entregues como enlace S2 la antigua página estática S1 sin comprobar que el backend S2 funciona.
2. **Enlace al repositorio GitHub actualizado** con archivos de este ZIP (`app.py`, `numericos.py`, `index.html`, `src/`, `docs/`, `tests/`, `README.md` y SQL).
3. **Informe de experimentos y fallos detectados**: archivo `docs/Informe_Experimentos_Semana2_UMSA.pdf` (puedes adjuntar también Word, pero el PDF conserva mejor el formato).

El ZIP completo puede adjuntarse adicionalmente como respaldo si Classroom lo permite. La base SQLite se crea al guardar, y no se incluyen datos de prueba en el ZIP.

## Revisión previa a «Entregar»
- [ ] El docente puede entrar al enlace público desde otro dispositivo.
- [ ] Los cuatro módulos ejecutan el escenario NORMAL con dos gráficos y tabla de métodos.
- [ ] ESTRÉS y MAL CONDICIONADO ejecutan y muestran sensibilidad/error.
- [ ] Se puede guardar un experimento y recuperarlo después de reiniciar la aplicación.
- [ ] El PDF coincide con los cálculos y los fallos reportados.
- [ ] El repositorio incluye código, SQL, DER y pruebas; no incluye bases personales o temporales.

## Actualización de alojamiento (versión corregida)

La aplicación ahora detecta el puerto de Render. Se incluye `render.yaml`; para que lo reconozca, súbelo a la raíz del repositorio junto con `app.py`. Render Free no proporciona almacenamiento persistente: una demostración temporal puede servir para ver los cálculos, pero el historial no sobrevivirá necesariamente a un redespliegue. Se requiere un servicio con disco para garantizarlo. GitHub Pages solo muestra contenido estático y **no** ejecuta la API ni la base SQLite. No entregues el enlace de GitHub Pages como aplicación completa de semana 2.
