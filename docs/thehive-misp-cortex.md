# Instalación de TheHive y su integración con MISP y Cortex

Este tutorial te guiará para instalar **TheHive**, y conectar **MISP** y **Cortex** para crear un flujo de análisis de incidentes en tu SOC.

---

## 🔹 1. Descargar e instalar TheHive

**TheHive** es una plataforma de gestión de incidentes de seguridad (SIEM/CSIRT).

### a) Agregar repositorio e instalar

1. Importa la clave pública:

```bash
wget -qO - https://dl.bintray.com/thehive-project/gpg.key | sudo apt-key add -
Añade el repositorio:

echo "deb https://dl.bintray.com/thehive-project/debian-stable main" | sudo tee /etc/apt/sources.list.d/thehive.list
Actualiza e instala TheHive:

sudo apt update
sudo apt install thehive -y
Inicia el servicio y habilítalo al arranque:

sudo systemctl enable thehive
sudo systemctl start thehive
🔹 Accede a TheHive desde el navegador: http://IP_DEL_SERVIDOR:9000



🔹 2. Integrar MISP en TheHive
MISP es una plataforma de inteligencia de amenazas que permite compartir indicadores de compromiso (IoCs).

a) Crear conexión a MISP
Ve a TheHive → Admin → MISP.

Haz clic en Add MISP Instance.

Completa los datos:

Name: nombre de tu instancia MISP

URL: dirección del servidor MISP

API key: clave de tu usuario MISP

Activa Sync events and attributes para que se sincronicen los datos automáticamente.


🔹 3. Integrar Cortex en TheHive
Cortex permite automatizar análisis de observables (IPs, hashes, dominios, etc.).

a) Instalar Cortex

sudo apt install cortex -y

b) Añadir Cortex en TheHive
Ve a TheHive → Admin → Cortex.

Haz clic en Add Cortex.

Completa los datos:

Name: nombre del servidor Cortex

URL: dirección de Cortex

API key: clave generada en Cortex

c) Probar la integración
Crea un caso en TheHive.

Añade un observable (por ejemplo, una IP sospechosa).

Lanza un análisis usando Cortex.

Si todo funciona correctamente, verás los resultados dentro de TheHive y podrás exportar indicadores a MISP.



