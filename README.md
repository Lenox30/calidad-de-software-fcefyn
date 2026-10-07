# Gestión y Calidad de Software — Trabajos prácticos

Trabajos prácticos de la materia optativa **Gestión y Calidad de Software** — FCEFyN, Universidad Nacional de Córdoba (2025).
Trabajo grupal (4 integrantes).

Cada carpeta es un práctico independiente sobre una herramienta o técnica que se usa en equipos de desarrollo reales.

| Práctico | Tema | Tecnologías |
|---|---|---|
| [`tp1-feature-flags-docker`](tp1-feature-flags-docker/) | Contenerizar una app y activar funcionalidades sin redeploy: dark launch, targeting por segmentos y A/B testing con feature flags | Python (Flask), Redis, Docker, Docker Compose, Harness Feature Flags |
| [`tp2-sonarqube-ci`](tp2-sonarqube-ci/) | Análisis estático de código en cada push y hooks de calidad antes de cada commit | SonarQube, GitHub Actions, pre-commit (black, isort, mypy) |
| [`tp4-canary-kubernetes-k6`](tp4-canary-kubernetes-k6/) | Despliegue canary: liberar una versión nueva a un porcentaje del tráfico y medir con pruebas de carga | Kubernetes (Minikube), NGINX Ingress, Docker, K6 |

## Resumen de cada práctico

**TP1 — Feature flags y Docker.** Contador de visitas en Flask con Redis, empaquetado con Docker y Docker Compose. Con Harness Feature Flags se prueba un *dark launch* (activar un cambio sin redeploy), *targeting* por segmentos de usuarios y A/B testing.

**TP2 — SonarQube y CI.** Sobre el juego del TP de Ingeniería de Software (repositorio privado) se configuró un pipeline de GitHub Actions que corre SonarQube en cada push o pull request, más hooks de pre-commit para formato (black, isort) y tipado (mypy). En esta carpeta están los archivos de configuración; el código analizado no está publicado.

**TP4 — Canary release y pruebas de carga.** Dos versiones de una app desplegadas en Kubernetes, con un NGINX Ingress que reparte el tráfico por porcentaje (canary). Se fue aumentando el porcentaje de la versión nueva y se midió el comportamiento con pruebas de carga en K6. El paso a paso está en el [README del práctico](tp4-canary-kubernetes-k6/README.md).

## Qué aprendimos

- Que la calidad no es solo testear al final: se puede automatizar en cada commit (pre-commit), en cada push (CI + SonarQube) y en cada release (canary + pruebas de carga).
- A separar el despliegue del lanzamiento de una funcionalidad con feature flags.
- A reducir el riesgo de una versión nueva exponiéndola de a poco y midiendo antes de pasarla a todos.
