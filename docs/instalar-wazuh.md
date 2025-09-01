**- ¿Qué es Wazuh?**

Es un SIEM (Security Information and Event Management) y HIDS (Host-based Intrusion Detection System).
Permite recopilar y analizar eventos de seguridad en tiempo real.
Funciona en Linux, Windows, macOS y contenedores.

**- ¿Para qué sirve?**

Detección de intrusiones
Monitorear logs y procesos en busca de comportamientos maliciosos.
Detecta intentos de fuerza bruta, escaladas de privilegios o accesos no autorizados.
Gestionar vulnerabilidades
Escanea equipos y detecta software vulnerable.
Permite priorizar parches de seguridad.
Monitorización de integridad
Supervisa cambios en archivos críticos del sistema.
Útil para detectar modificaciones sospechosas en configuraciones o binarios.
Respuesta automatizada



**# Integración de Wazuh en Kali Linux**

## 1. Instalar dependencias
sudo apt update && sudo apt upgrade -y
sudo apt install curl apt-transport-https lsb-release gnupg2 -y
2. Instalar el agente de Wazuh
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
echo "deb https://packages.wazuh.com/4.x/apt stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
sudo apt update
sudo apt install wazuh-agent -y
3. Configurar el agente
Edita /var/ossec/etc/ossec.conf y apunta al servidor Wazuh Manager:

xml
Copiar código
<client>
  <server>
    <address>IP_DEL_MANAGER</address>
    <port>1514</port>
    <protocol>tcp</protocol>
  </server>
</client>
4. Iniciar el agente
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent

**En este caso yo lo hice en una máquina Kali Linux, si no tienes tanto espacio en tu ordenador, para crear una maquina virtual, tmabien existe la opcion de instalar una .ova, no te olvides de actualizarla e instalarle servicios que no vienen activos como python.**
