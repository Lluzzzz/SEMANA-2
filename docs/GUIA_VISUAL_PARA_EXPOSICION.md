# BIOPRINT-VASC: guía visual para explicar el proyecto

## Qué mostrar en el video (guía, no obligación de semana 2)

| Voz | Mostrar en pantalla | Explicación breve |
|---|---|---|
| Integrante 1 | Portada y visualizador de microcanales | El oxígeno parte del canal, difunde y se consume en un hidrogel modelado de forma simplificada. |
| Integrante 2 | Cuatro tarjetas y tablas de métodos | Interpolación, raíces, integración, sistemas lineales y Runge–Kutta; comparar errores y referencias, no solo mostrar fórmulas. |
| Integrante 3 | Entrar a los cuatro módulos | Explicar en una frase el objetivo de cada caso; cambiar parámetros y ejecutar los cálculos. |
| Integrante 4 | Mover separación 0,30 a 0,80 mm, comparar gráficos, guardar e historial | La concentración normalizada mínima calculada pasa de 0,811 a 0,325 para el modelo de ejemplo. Conservar las unidades y aclarar sus límites. |

Las cuatro imágenes de las tarjetas y sus banners son ilustraciones conceptuales originales; no representan datos experimentales ni visualizaciones 3D calculadas. El campo de oxígeno, su curva y el porcentaje bajo un umbral proceden del modelo analítico unidimensional que se representa repetido en una geometría 2D idealizada. No representan porcentajes de células vivas o muertas ni una simulación clínica.

## Contenido incorporado a la web
- Cuatro imágenes en las tarjetas, optimizadas para web y disponibles sin conexión con servicios externos.
- Banner con imagen y dos explicaciones breves dentro de cada módulo: objetivo y resultados esperados.
- Secuencia de tres ideas entre la portada y el visualizador (suministro → transporte → comparación).
- Ayuda desplegable en el visualizador para interpretar colores y umbrales.

## Ejecución

En la carpeta del proyecto: `python app.py`. Abre http://127.0.0.1:8000 en el navegador. El ZIP completo se sube descomprimido al repositorio GitHub. Render usa `render.yaml` para el servicio Python; GitHub Pages por sí solo no ejecuta SQLite y Python.
