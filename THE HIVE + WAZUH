**# Integración de Wazuh con TheHive**

Cómo conectar **TheHive** con **Wazuh**, de manera que las alertas generadas por Wazuh se reflejen automáticamente como incidentes en TheHive.


**## 1. Requisitos**

- Wazuh Manager en funcionamiento.
- TheHive instalado y accesible.
- Permisos para generar API keys en TheHive.

**## 2. Configurar Wazuh para enviar alertas**

Wazuh puede enviar alertas mediante **webhooks** hacia TheHive.

### a) Editar el archivo de configuración
sudo nano /var/ossec/etc/ossec.conf
Agrega la sección de integración para TheHive:

xml
Copiar código
<integration>
  <name>thehive</name>
  <hook_url>http://IP_THEHIVE:9000/api/alert</hook_url>
  <level>10</level>
</integration>
hook_url: la URL del endpoint de TheHive que recibe alertas.

level: nivel mínimo de alerta que quieres enviar.

**3. Crear API key en TheHive**
Ve a TheHive → Admin → Users → API Key.

Copia la clave generada.

Usar esta clave en el conector Wazuh → TheHive.

**4. Conector (Webhook o script)**
Para que Wazuh envíe alertas, necesitas un script o conector que transforme los eventos de Wazuh en alertas de TheHive.
Ejemplo simple usando Python:

python
Copiar código
import requests
import json

API_KEY = "TU_API_KEY_THEHIVE"
THEHIVE_URL = "http://IP_THEHIVE:9000/api/alert"

def enviar_alerta(evento):
    headers = {"Authorization": f"Bearer {API_KEY}", "Content-Type": "application/json"}
    data = {
        "title": f"Alerta Wazuh: {evento['rule']['description']}",
        "description": json.dumps(evento, indent=2),
        "type": "external",
        "source": "Wazuh",
        "severity": evento['rule']['level']
    }
    response = requests.post(THEHIVE_URL, headers=headers, json=data)
    print(response.status_code, response.text)
Este script se puede llamar desde Wazuh usando active response o mediante un Webhook.

**5. Verificar la integración**
Genera un evento de prueba en Wazuh (por ejemplo, un escaneo de puertos).

Comprueba que el evento aparezca en TheHive → Alerts.

Si todo funciona, las alertas de Wazuh se convertirán automáticamente en incidentes en TheHive.
