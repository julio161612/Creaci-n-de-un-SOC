# Creación de un SOC
Laboratorio de seguridad informática integrando Wazuh, TheHive, Cortex y MISP para gestión de incidentes

---

### 📚 Tutoriales
- [Instalar Wazuh](instalar-wazuh.md)
- [TheHive + MISP + Cortex](thehive-misp-cortex.md)
- [TheHive + Wazuh](thehive-wazuh.md)

### 📁 Capturas
- [CORTEX](capturas/CORTEX/index.md)
- [MISP](capturas/MISP/index.md)
- [WAZUH](capturas/WAZUH/index.md)
- [Flujo](capturas/flujo/index.md)
- [THE_HIVE](capturas/THE_HIVE/index.md)

---

## Diagrama SOC

![Diagrama SOC](capturas/dashboard/Captura%20desde%202025-08-31%2018-02-30.png)

El diagrama muestra cómo los distintos elementos del SOC interactúan:

- **PCs / Usuarios**: Generan logs y alertas de seguridad.
- **Wazuh Agent**: Recopila logs y los envía al servidor Wazuh.
- **Wazuh Server**: Centraliza alertas y envía incidentes a TheHive.
- **TheHive**: Gestiona incidentes y asigna tareas a analistas.
- **Cortex**: Analiza automáticamente incidentes o archivos.
- **MISP**: Proporciona inteligencia de amenazas para enriquecer los análisis.

![Flujo TheHive](capturas/dashboard/06.png)

## Objetivo

- Centralizar alertas de seguridad en un único panel.
- Automatizar análisis de incidentes.
- Integrar inteligencia de amenazas para mejorar la respuesta SOC.

## Tecnologías utilizadas

- **Wazuh**: Monitorización de logs y detección de amenazas
- **TheHive**: Gestión de incidentes
- **Cortex**: Análisis automatizado
- **MISP**: Inteligencia de amenazas
- **Linux**: Máquina virtual para despliegue

## Flujo del proyecto

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

