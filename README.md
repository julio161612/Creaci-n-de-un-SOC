# Creacion de un SOC
Laboratorio de seguridad informática integrando Wazuh, TheHive, Cortex y MISP para gestión de incidentes

<img width="758" height="664" alt="Captura desde 2025-08-31 18-02-30" src="https://github.com/user-attachments/assets/2bac85c6-8303-4ead-984c-df82c638a4b5" />

El diagrama muestra cómo los distintos elementos del SOC interactúan:

- **PCs / Usuarios**: Generan logs y alertas de seguridad.
- **Wazuh Agent**: Recopila logs y los envía al servidor Wazuh.
- **Wazuh Server**: Centraliza alertas y envía incidentes a TheHive.
- **TheHive**: Gestiona incidentes y asigna tareas a analistas.
- **Cortex**: Analiza automáticamente incidentes o archivos.
- **MISP**: Proporciona inteligencia de amenazas para enriquecer los análisis.




<img width="927" height="963" alt="26, ya estan los casos en the hive" src="https://github.com/user-attachments/assets/9908f84a-2b93-4e9b-a3b0-9f5590c56057" />




## Objetivo

- Centralizar alertas de seguridad en un único panel.
- Automatizar análisis de incidentes.
- Integrar inteligencia de amenazas para mejorar la respuesta SOC.

- ## Tecnologías utilizadas

- **Wazuh**: Monitorización de logs y detección de amenazas
- **TheHive**: Gestión de incidentes
- **Cortex**: Análisis automatizado
- **MISP**: Inteligencia de amenazas
- **Linux**: Máquina virtual para despliegue

- ## Flujo del proyecto

Wazuh detecta alertas → TheHive gestiona incidentes → Cortex analiza automáticamente → MISP proporciona inteligencia de amenazas

## Cómo replicarlo

1. Instalar Wazuh en una máquina virtual o servidor
2. Configurar TheHive conectado a Wazuh
3. Integrar Cortex para análisis automático
4. Conectar MISP para inteligencia de amenazas
5. Probar flujo generando alertas


## Contacto

- [LinkedIn](https://www.linkedin.com/in/julio-lópez-cotán-1032aa348)
- Correo: juliolopezcotan6@gmail.com
- Portafolio: [PORTAFOLIO SOC](https://julio161612.github.io/Creaci-n-de-un-SOC/)
