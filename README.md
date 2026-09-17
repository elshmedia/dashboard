# 📊 ELSH MEDIA - Operations Dashboard

Este repositorio público actúa exclusivamente como la **capa de presentación estática (Frontend)** para la consola de monitoreo, telemetría y observabilidad de la red internacional de medios de **ELSH MEDIA**.

El sitio web está alojado de forma gratuita utilizando **GitHub Pages** y se actualiza de manera automatizada mediante un pipeline de GitOps (Event-Driven) inyectado de forma local desde los servidores privados de la organización.

---

## 🌐 Consola en Vivo

La matriz operativa, los KPIs globales de la red y el estado analítico de los nodos de contenido pueden visualizarse en tiempo real a través del siguiente enlace:

👉 <span><a href="https://elshmedia.github.io/dashboard" target="_blank" rel="noopener noreferrer">Abrir Dashboard en una nueva pestaña ↗</a></span>

---

## 🏗️ Arquitectura de Archivos (Costo \$0)

Para garantizar la máxima seguridad de la infraestructura y mantener el secreto comercial de las estrategias de automatización, este repositorio **no contiene código fuente ejecutable, plantillas de diseño de contenido (Charts) ni credenciales de red**. 

El repositorio está compuesto únicamente por dos componentes estáticos livianos:

*   `index.html`: Una interfaz de usuario reactiva con diseño oscuro estilo cyberpunk maquetada con HTML5 nativo y **Tailwind CSS**. Incluye motores de filtrado, ordenamiento dinámico por horas de reproducción y buscador en tiempo real.
*   `metrics.json`: El almacén de estado estático (State Store) que contiene las estadísticas agregadas de suscriptores, horas de reproducción y estado de monetización de la red.

---

## 🔄 Flujo de Sincronización (GitOps Pipeline)

Los datos de este repositorio nunca se editan de forma manual. El ciclo de actualización nocturno sigue el siguiente protocolo de infraestructura:

1.  **Ingesta:** El motor privado `media-orchestrator` se ejecuta localmente y extrae la telemetría depurada directo desde las plataformas de distribución.
2.  **Compilación:** El motor procesa los datos y sobrescribe el archivo estático local `metrics.json`.
3.  **Despliegue:** El script automatizado `deploy_metrics.sh` detecta las diferencias, realiza el *commit* de los datos actualizados y ejecuta un `git push` hacia la rama principal de este repositorio público, gatillando el despliegue automático de GitHub Pages en segundos.

---

## 🔒 Directiva de Seguridad de la Información

> 📢 **Aviso de Privacidad:** Toda la información expuesta en esta consola corresponde a métricas públicas consolidadas de rendimiento de canales de distribución y portales web abiertos. Los manifiestos de configuración, las cuentas de infraestructura de Inteligencia Artificial (InVideo, OpenAI, Midjourney) y los guiones de producción se encuentran protegidos bajo llave dentro del perímetro de seguridad de los repositorios privados de la organización `elshmedia`.
