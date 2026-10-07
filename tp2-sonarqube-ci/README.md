# TP2 — Análisis estático con SonarQube y hooks de pre-commit

El código analizado es el juego del TP de Ingeniería de Software: [Lenox30/SHXL-GCS](https://github.com/Lenox30/SHXL-GCS). Esta carpeta contiene una copia de la configuración de calidad que se agregó a ese proyecto (en el repo original los archivos llevan punto adelante: `.pre-commit-config.yaml` y `.github/workflows/build.yml`).

| Archivo | Para qué sirve |
|---|---|
| `github-actions-sonarqube.yml` | Pipeline de GitHub Actions que corre el análisis de SonarQube en cada push a `main` y en cada pull request. En el proyecto original está en `.github/workflows/build.yml`. |
| `sonar-project.properties` | Configuración del proyecto en SonarQube: qué carpetas analizar (backend en Python y frontend en JavaScript). |
| `pre-commit-config.yaml` | Hooks que corren antes de cada commit: formato con **black** e **isort**, tipado con **mypy** y bloqueo de archivos demasiado grandes. |

El token de SonarQube no está en el repositorio: se lee desde los *secrets* de GitHub (`SONAR_TOKEN`).
