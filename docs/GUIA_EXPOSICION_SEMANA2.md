# Guía de presentación — UMSA · Semana 2

**Orden de demostración (aprox. 5 minutos si el docente no fijó otro tiempo)**

1. **Integrante 1**: presentar la pregunta general BIOPRINT-VASC. Abrir el módulo de extrusión, calcular NORMAL y mostrar tres métodos de raíces, tres de integración y RK2/RK4. Explicar unidades de caudal y volumen y que no son mediciones reales.
2. **Integrante 2**: módulo de degradación. Comparar bisección, Newton y secante, luego resolver calibración SPD 4×4 con Jacobi, Gauss-Seidel, LU, CG y referencia. Mostrar residuo y condición.
3. **Integrante 3**: módulo de oscilaciones. Explicar EDO `m·x''+c·x'+k·x=0`, comparación RK2 frente a RK4, dos gráficos e integración de `x²(t)`.
4. **Integrante 4**: módulo de sensores. Mostrar Lagrange, Newton por diferencias divididas y splines; activar ESTRES y MAL CONDICIONADO y explicar el benchmark de Runge. Ir a Historial, abrir un registro y pulsar **Repetir y verificar**.

**Prueba de BD antes de la defensa:** ejecutar `python app.py`, entrar en la web, cambiar un parámetro, calcular, guardar, cerrar el servidor con Ctrl+C, iniciarlo de nuevo, entrar en Historial, recuperar, repetir y comprobar el SHA-256.

**Preguntas probables:**
- ¿Por qué Simpson exige `n` par? Porque cada grupo de dos subintervalos integra una interpolación cuadrática.
- ¿Qué variante de RK2? Punto medio explícito: `k₂=f(t+h/2, y+h k₁/2)`.
- ¿Por qué CG es apropiado para el sistema lineal? Su matriz 4×4 se construye simétrica y definida positiva.
- ¿El escenario de estrés equivale a mal condicionado? No. Estrés modifica parámetros del modelo; el mal condicionamiento se demuestra con sensibilidad matemática.
- ¿Un residuo pequeño garantiza un resultado exacto? No; depende del condicionamiento, la discretización y la referencia.
- ¿Qué guarda SQLite? Entradas, escenario, fecha, métodos, trazas, errores, referencias, conclusiones y gráficos serializados; además SHA-256 del resultado.

La demostración está diseñada para 4 integrantes; todos deben poder explicar los métodos generales. El tema fue aprobado por el docente, según la confirmación del equipo.
