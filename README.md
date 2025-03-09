# Servicio de Correos - Node.js y Express

Este es un servicio de envío de correos electrónicos desarrollado con **Node.js**, **Express**, **Nodemailer** y **OAuth2 de Google**. El servicio soporta HTTPS utilizando certificados de **Let's Encrypt**.

## 🚀 Características
- Envío de correos electrónicos mediante **Gmail API** y OAuth2.
- Implementación de HTTPS con certificados SSL en producción.
- Configuración flexible con **variables de entorno**.
- Soporte para **CORS**.

## 📌 Requisitos Previos
Antes de ejecutar el proyecto, asegúrate de tener:
- **Node.js** instalado en tu máquina.
- Una cuenta de **Google Cloud** con OAuth2 configurado.
- Un dominio registrado en **DuckDNS** (o cualquier otro proveedor).

## 🛠 Configuración
### 1️⃣ Clonar el Repositorio
```bash
git clone https://github.com/Jcss1462/ServicioCorreos.git
cd ServicioCorreos
```

### 2️⃣ Instalar Dependencias
```bash
npm install
```

### 3️⃣ Configurar Variables de Entorno
El archivo **.env** no está incluido en el repositorio por seguridad. Debes crearlo manualmente en la raíz del proyecto y agregar las siguientes variables:

```ini
# Configuración del Servidor
PORT=8443
ENVIRONMENT=production # Cambia a 'development' si usas certificados locales

# Configuración de Gmail API (OAuth2)
CLIENT_ID=tu_client_id
CLIENT_SECRET=tu_client_secret
REFRESH_TOKEN=tu_refresh_token
EMAIL_USER=tu_correo@gmail.com
```

### 4️⃣ Ejecutar el Servidor
```bash
node server.js
```

### 🛡 Certificados SSL con Let's Encrypt
Si estás en producción, asegúrate de que los certificados SSL de Let's Encrypt estén configurados en:
```
/etc/letsencrypt/live/jcss1462mailsender.duckdns.org/
```
Estos certificados se deben renovar automáticamente con:
```bash
sudo certbot renew --quiet
```

Para verificar la renovación:
```bash
sudo certbot renew --dry-run
```

## 📬 Uso de la API
### Enviar un Correo
**Endpoint:**
```
POST /send-email
```
**Body (JSON):**
```json
{
  "to": "destinatario@example.com",
  "subject": "Asunto del correo",
  "text": "Contenido del mensaje"
}
```

## 🔗 Tecnologías Utilizadas
- **Node.js** y **Express.js**
- **OAuth2 de Google**
- **Nodemailer**
- **Certificados SSL (Let's Encrypt)**

