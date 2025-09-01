# Instalar Wazuh

Este tutorial te guiará en la instalación y configuración de **Wazuh**, un sistema de monitorización y detección de amenazas, en un entorno de laboratorio de seguridad. Incluye capturas y ejemplos de comandos.

---

## 🔹 Objetivo

- Configurar un servidor Wazuh.
- Conectar agentes desde máquinas Linux y Windows.
- Verificar la recepción de logs y alertas en el panel de Wazuh.

---

## 🔹 Requisitos

- Una máquina virtual o servidor Linux (Ubuntu 22.04 recomendado).  
- Conexión a Internet.  
- Acceso a la terminal con permisos de administrador.

---

## 1️⃣ Actualizar el sistema

Antes de instalar, asegurémonos de que los paquetes estén actualizados:

sudo apt update && sudo apt upgrade -y
- Esto garantiza compatibilidad con los repositorios de Wazuh y evita errores de instalación.

2️⃣ Añadir el repositorio de Wazuh
Agrega el repositorio oficial de Wazuh a tu sistema:

curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo gpg --dearmor -o /usr/share/keyrings/wazuh-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/wazuh-archive-keyring.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
sudo apt update
3️⃣ Instalar el servidor Wazuh

sudo apt install wazuh-manager -y
sudo systemctl enable wazuh-manager
sudo systemctl start wazuh-manager
sudo systemctl status wazuh-manager
🔹 Verifica que el servicio esté activo y funcionando correctamente.



4️⃣ Configurar agentes Wazuh
4.1. Agente Linux

sudo apt install wazuh-agent -y
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
Reemplaza la IP del servidor en /var/ossec/etc/ossec.conf si tu servidor está en otra máquina.



4.2. Agente Windows
Descarga el instalador desde la página oficial.

Ejecuta el instalador y proporciona la IP del servidor Wazuh.

Inicia el servicio del agente.



5️⃣ Verificación en el panel Wazuh
Accede al dashboard desde tu navegador (http://tu-servidor:55000).

Comprueba que los agentes estén conectados y enviando logs.

Observa cómo las alertas se generan en tiempo real.



6️⃣ Personalizaciones y ajustes
Modifica reglas de alertas según tus necesidades.

Configura notificaciones por correo.

Integra con TheHive para gestión de incidentes.

 OPINIÓN PERSONAL: la mejor opción es intalarlo en Kali Linux, pero el inconveniente es la gran cantidad de espacio de la que tienes que disponer. Una solución es intalar una ova, no te olvides de actualizarla e instalar pyhton.
