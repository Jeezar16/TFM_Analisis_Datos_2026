# TFM: Riesgo de Fondeo BCR y Oligopolio Bancario
**Autor:** Jeferson Arias Méndez

**Año:** 2026

Este repositorio contiene el pipeline automatizado de extracción, limpieza y modelado de datos macroeconómicos y crediticios de Costa Rica para el Trabajo Final de Máster.

## Arquitectura del Proyecto
- `notebooks/`: Contiene el código fuente en Google Colab con la lógica del ETL y Machine Learning. Además del file de Tableau.
- `data/`: Datasets extraídos automáticamente del BCCR y la SUGEF, listos para ser consumidos por Tableau.

---

## Protocolo de Extracción Manual (Respaldo)
En caso de que las APIs bancarias cambien su infraestructura de seguridad o bloqueen las IPs de Google Cloud, los datos deben extraerse y actualizarse manualmente desde las siguientes fuentes oficiales:

### 1. SUGEF (Sistema Bancario Nacional)
*   **Enlace directo:** [Reporte de Encaje Legal e Información Crediticia](https://www.sugef.fi.cr/rsw_reportes/ReporteEncajeLegal)
*   **Ruta:** *Información crediticia -> Cartera de crédito a partir de 2024 (y pre-2024) -> Categoría de Riesgo.*
*   **Formato de descarga:** En Tableau, clic en `...` -> Exportar Datos -> Datos con diseño actual.

### 2. Banco Central de Costa Rica (BCCR)
*   **Enlace directo:** [Indicadores Macroeconómicos (Cuadro 1016)](https://sdd.bccr.fi.cr/es/IndicadoresEconomicos/Inicio/Contenedor/969?Cuadro=1016)
*   **Instrucciones para cURL:** Presionar `F12` (Network), hacer clic en el botón de descarga y copiar el evento `DescargueCsv` como *cURL (bash)* para inyectarlo en Colab.

*Nota: Al ejecutarse el código en Colab para extraer los datos actuales en vivo, pedirá el token de GitHub, el cual será proporcionado directamente en un archivo .txt*
---
*Pipeline construido en Python (Colab) y sincronizado mediante PyGithub.*
