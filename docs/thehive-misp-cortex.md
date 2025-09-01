**# Instalación de TheHive y su integración con MISP y Cortex**

**## 1. Descargar e instalar TheHive**

TheHive es una plataforma de gestión de incidentes de seguridad (SIEM/CSIRT).  

**### a) Agregar repositorio e instalar**
```bash
# Importar la clave pública
wget -qO - https://dl.bintray.com/thehive-project/gpg.key | sudo apt-key add -

# Añadir el repositorio
echo "deb https://dl.bintray.com/thehive-project/debian-stable main" | sudo tee /etc/apt/sources.list.d/thehive.list

# Actualizar e instalar
sudo apt update
sudo apt install thehive
**b) Iniciar TheHive**
sudo systemctl enable thehive
sudo systemctl start thehive
Accede a TheHive desde el navegador: http://IP_DEL_SERVIDOR:9000

**2. Integrar MISP en TheHive**
MISP es una plataforma de inteligencia de amenazas que permite compartir indicadores de compromiso (IoCs).

**a) Crear conexión a MISP**
Ve a TheHive → Admin → MISP.

Haz clic en Add MISP Instance.

Completa:

Name: nombre de tu instancia MISP

URL: dirección del servidor MISP

API key: la clave de tu usuario MISP

Activa Sync events and attributes para que se sincronicen los datos.

**3. Integrar Cortex en TheHive**
Cortex permite automatizar análisis de observables (IPs, hashes, dominios, etc.).

**a) Instalar Cortex**
sudo apt install cortex
**b) Añadir Cortex en TheHive**
Ve a TheHive → Admin → Cortex.

Haz clic en Add Cortex.

Completa:

Name: nombre del servidor Cortex

URL: dirección de Cortex

API key: clave generada en Cortex

**c) Probar la integración**
Crea un caso en TheHive.

Añade un observable (por ejemplo, una IP sospechosa).

Lanza un análisis usando Cortex.

Si todo está correcto, verás los resultados dentro de TheHive y podrás exportar indicadores a MISP.
