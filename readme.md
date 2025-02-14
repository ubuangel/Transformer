# Predicción de Estrés usando un Transformer con Señal EDA

Este proyecto se enfoca en entrenar un modelo Transformer con un solo codificador para predecir niveles de estrés utilizando la señal de **Actividad Electrodérmica (EDA)**. Se emplea la base de datos **WESAD** y se utiliza la API de **Neptune** para el seguimiento y gestión de experimentos. El desarrollo se realiza en un entorno virtual con **Conda** y **Python 3.11**, desplegado en un sistema **Ubuntu 22.04** con las siguientes características de hardware: **Intel Core i7**, **8 núcleos**, **16 GB de RAM**.

## Tabla de Contenidos

- [Introducción](#introducción)
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Arquitectura del Modelo](#arquitectura-del-modelo)
- [Requisitos](#requisitos)
- [Instalación](#instalación)
- [Uso](#uso)
- [Resultados](#resultados)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)
- [Referencias](#referencias)

## Introducción

El estrés es una respuesta biológica frente a situaciones demandantes. La detección temprana del estrés es crucial para prevenir problemas de salud. La señal EDA es un indicador fiable de la actividad del sistema nervioso simpático, y su análisis puede proporcionar información valiosa sobre los niveles de estrés de un individuo.

## Descripción del Proyecto

Este proyecto:

- Entrena un modelo Transformer con un solo codificador para predecir el estrés a partir de señales EDA.
- Utiliza la base de datos WESAD, un conjunto de datos multivariados para la detección del estrés y afecto.
- Implementa el seguimiento de experimentos con la API de Neptune, permitiendo un monitoreo detallado.
- Está desarrollado en un entorno virtual con Conda y Python 3.11, asegurando una configuración reproducible.
- Se despliega en Ubuntu 22.04 con hardware optimizado para tareas de cómputo intensivo.

## Arquitectura del Modelo

El modelo Transformer utiliza un único codificador para procesar las secuencias temporales de la señal EDA. La arquitectura se ha adaptado para capturar características temporales y no lineales presentes en las señales fisiológicas.

![Arquitectura del Transformer](docs/transformer_architecture.png)

## Requisitos

- **Sistema Operativo**: Ubuntu 22.04
- **Hardware**:
  - CPU: Intel Core i7 (8 núcleos)
  - RAM: 16 GB
- **Software**:
  - Python 3.11
  - Conda
- **Librerías de Python**:
  - numpy
  - pandas
  - matplotlib
  - keras
  - neptune-client

## Instalación

1. **Clonar el repositorio**:

   ```bash
   git clone https://github.com/tu_usuario/eda-stress-transformer.git
   cd eda-stress-transformer
   ```

2. **Crear el entorno virtual con Conda**:

   ```bash
   conda create -n eda-transformer python=3.11
   conda activate eda-transformer
   ```

3. **Instalar las dependencias**:

   ```bash
   pip install -r requirements.txt
   ```

   *Asegúrate de que el archivo `requirements.txt` incluya todas las librerías necesarias.*

## Uso

1. **Descargar la base de datos WESAD**:

   - Regístrate y descarga el conjunto de datos desde el [sitio oficial](https://archive.ics.uci.edu/ml/datasets/WESAD).
   - Extrae los archivos y colócalos en la carpeta `data/wesad`.

2. **Configurar Neptune**:

   - Crea una cuenta en [Neptune](https://neptune.ai/).
   - Obtén tu API token y configúralo en el archivo `.env` o exporta la variable de entorno:

     ```bash
     export NEPTUNE_API_TOKEN='tu_api_token'
     ```

3. **Entrenar el modelo**:

   Ejecuta el script de entrenamiento:

   ```bash
   python train.py
   ```

   *El script cargará los datos, entrenará el modelo y registrará los resultados en Neptune.*

## Resultados

Los resultados del entrenamiento incluyen:

- **Métricas de rendimiento**: precisión, pérdida, etc.
- **Gráficas de aprendizaje**: evolución de las métricas durante el entrenamiento.
- **Modelo guardado**: el modelo entrenado se almacenará en la carpeta `models`.

Puedes visualizar los resultados detallados en tu panel de Neptune.

## Contribuciones

¡Las contribuciones son bienvenidas! Si deseas colaborar:

1. Haz un fork del proyecto.
2. Crea una rama con la nueva característica o corrección de errores:

   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```

3. Realiza tus cambios y haz commit:

   ```bash
   git commit -m "Agrega nueva funcionalidad"
   ```

4. Envía tus cambios al repositorio remoto:

   ```bash
   git push origin feature/nueva-funcionalidad
   ```

5. Abre un Pull Request en GitHub.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.

## Referencias

- **WESAD Dataset**: [Wearable Stress and Affect Detection](https://archive.ics.uci.edu/ml/datasets/WESAD)
- **Neptune.ai**: [Neptune Documentation](https://docs.neptune.ai/)
- **Transformer Architecture**: [Vaswani et al., 2017](https://arxiv.org/abs/1706.03762)

---

**Notas adicionales**:

- **Optimización**: Se recomienda explorar técnicas de regularización y ajuste de hiperparámetros para mejorar el rendimiento del modelo.
- **Ampliación**: Considera integrar señales adicionales del conjunto de datos WESAD para enriquecer el modelo.
- **Soporte**: Si tienes preguntas o necesitas asistencia, no dudes en abrir un issue en el repositorio.
