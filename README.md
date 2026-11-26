<div align="center">

![Cloud](https://img.shields.io/badge/CLOUD-455A64?style=for-the-badge)

# Pipeline de datos en streaming en AWS

Arquitectura en AWS que captura publicaciones de Mastodon en tiempo real, analiza su sentimiento con un modelo de Hugging Face y las presenta en un dashboard.

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=white) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

<img src="Actividad%20-%20Implementacion%20AWS%20%28M6-ES%29/iconos_flujo_trabajo/Flujo%20de%20trabajo%20AWS.png" alt="Diagrama del flujo de datos en AWS: productor en EC2, Kinesis, Lambda, S3, Athena y dashboard" width="100%" />

<sub>Flujo de trabajo de la arquitectura.</sub>

</div>

---

## Descripción general

Flujo de datos escalable para ingerir y procesar texto no estructurado. Un productor en EC2 lee publicaciones de Mastodon y las envía a Kinesis; funciones Lambda las guardan en S3 y las enriquecen con un análisis de sentimiento mediante la API de Hugging Face; Athena permite consultarlas con SQL y un dashboard en Streamlit las visualiza.

El repositorio incluye también los laboratorios de AWS Academy Cloud Foundations que sirven de base teórica.

## Funcionalidades

- **Ingesta:** productor en EC2 que publica en un flujo de Kinesis.
- **Procesamiento:** funciones Lambda de Kinesis a S3 y de análisis de sentimiento.
- **Secretos:** tokens de Mastodon y Hugging Face en Secrets Manager, no en el código.
- **Consulta:** tablas en Athena sobre los datos de S3.
- **Visualización:** dashboard en Streamlit.
- **Monitorización:** CloudWatch.

## Contenido

| Carpeta | Contenido |
| --- | --- |
| [Proyecto](Actividad%20-%20Implementacion%20AWS%20%28M6-ES%29) | Cuaderno del proyecto, funciones Lambda, dashboard, consulta SQL y explicación paso a paso con capturas |
| [Laboratorios](AWS%20Academy%20Cloud%20Foundations) | IAM, VPC, EC2, Lambda, Elastic Beanstalk, EBS, bases de datos, escalado y balanceo de carga |

## Tecnologías y herramientas

| Ámbito | Herramientas |
| --- | --- |
| Cómputo | EC2, Lambda |
| Datos | Kinesis, S3, Athena |
| Seguridad y operación | Secrets Manager, CloudWatch |
| Análisis y visualización | Hugging Face Inference API, Streamlit, boto3 |

## Instalación y uso

El proyecto se desplegó en el laboratorio de AWS Academy. Los pasos para crear cada servicio, con capturas, están en [`Explicación-paso-a-paso-del-proyecto.md`](Actividad%20-%20Implementacion%20AWS%20%28M6-ES%29/Explicaci%C3%B3n-paso-a-paso-del-proyecto.md).

## Aspectos técnicos destacados

- Arquitectura serverless orientada a eventos, de la ingesta a la visualización.
- Gestión de credenciales con Secrets Manager.
- Enriquecimiento de datos en tiempo real con un modelo de lenguaje.

## Autor

**Julio Úbeda Quesada** · Data Scientist

[![Portfolio](https://img.shields.io/badge/Portfolio-0B2545?style=flat-square&logo=astro&logoColor=white)](https://juliouq.github.io/Portfolio-Web---JulioUQ/es/) [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square)](https://www.linkedin.com/in/juliouq/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/JulioUQ)

<sub>Proyecto realizado en el Máster Universitario en Ciencia de Datos.</sub>
