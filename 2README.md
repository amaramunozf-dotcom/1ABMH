# Evaluación Bioinstrumental: Estabilidad Postural Unipodal Automática

## Descripción del Proyecto
Interfaz web interactiva desarrollada para la evaluación biomecánica y cuantitativa del control postural estático en apoyo unipodal (*Single Leg Stance Test*). La aplicación utiliza visión por computador mediante procesamiento de video en tiempo real para:

1. **Calibración Automática de la Línea Media ($X_0$):** Establece el eje de referencia vertical del tronco promediando la ubicación espacial de hombros y caderas durante la posición bípeda.
2. **Activación Gestual (*Contactless Trigger*):** Detecta la elevación de la mano derecha (palma por sobre el hombro) como señal autónoma para armar el inicio de la prueba.
3. **Reconocimiento del Pie de Apoyo:** Identifica biomecánicamente cuál extremidad sostiene la carga postural (Derecha o Izquierda) calculando la elevación del tobillo contralateral.
4. **Cuantificación en Tiempo Real:** Mide la duración del apoyo ($T$), la desviación instantánea mediolateral ($\Delta X$), la desviación máxima (*Peak Sway*) y la dispersión cuadrática media ($RMS$).
5. **Detención Automática por Doble Apoyo:** Monitorea la posición de ambos pies y detiene la medición e intervalos de tiempo tan pronto como el sujeto vuelve a hacer contacto con ambos pies en el piso.
6. **Reporte y Análisis Bioinstrumental:** Genera un gráfico lineal dinámico del desplazamiento postural y despliega una tabla final con el diagnóstico biomecánico e interpretación clínica.

## Requisitos y Dependencias
- **Navegador Web:** Google Chrome, Microsoft Edge, Mozilla Firefox o Safari (con soporte para WebGL y WebRTC).
- **Cámara Web:** Cámara frontal o externa con resolución recomendada de 720p o superior.
- **Conexión a Internet:** Requerida para la carga de bibliotecas desde CDN:
  - `MediaPipe Pose` v0.5 (Extracción de marcadores antropométricos en tiempo real)
  - `Chart.js` v3.x (Visualización gráfica de series de tiempo)
  - `Tailwind CSS` v3.x (Diseño de la interfaz de usuario)

## Instrucciones de Uso
1. **Acceso y Permisos:** Ingrese al enlace de la página web pública y permita el acceso a la cámara web.
2. **Posicionamiento:** Ubíquese frente a la cámara a una distancia de 1.5 a 2 metros en postura bípeda erguida.
3. **Calibración de Línea Media:** Verifique en pantalla la línea punteada vertical azul, la cual delimita el eje medio corporal de referencia.
4. **Señal de Inicio:** Levante la mano derecha con la palma visible por sobre el nivel del hombro. El indicador de estado cambiará a color azul.
5. **Ejecución Unipodal:** Eleve la pierna que prefiera. La interfaz detectará automáticamente el pie de apoyo, iniciará el cronómetro y graficará las oscilaciones posturales en directo.
6. **Finalización del Test:** Apoye ambos pies sobre el piso. La interfaz detectará el doble contacto, detendrá el análisis e imprimirá la tabla de resumen bioinstrumental.

## Estructura de Archivos del Repositorio
- `index.html`: Código fuente unificado que contiene la estructura HTML, estilos, script de visión por computador, lógica de maquina de estados, gráficos y generación de reporte.
- `README.md`: Documentación completa del proyecto, requisitos del sistema, arquitectura biomecánica y tutorial de uso.