# $IOT-IOB-GENERATIVE-IA-SPRINT01$

## **Objetivo**

Utilizar IOT para rastrear uma moto no patio da MOTTU, triangulando a localização com o uso de WIFI.

Desenvolver um protótipo funcional utilizando **ESP32**, que se conecta a um **broker MQTT** hospedado em uma **VM Linux (Azure)** com **Mosquitto** e **Node-RED**.

---

## **Funcionalidades**

- Conexão Wi-Fi
- Publicação de dados via **MQTT**
- Dados enviados no formato **JSON**
- Visualização em tempo real no **Node-RED**
- Infraestrutura hospedada na **Azure**, com uso de **Docker Compose**

---

## **Tecnologias Utilizadas**

- ESP32
- WiFi.h
- PubSubClient (MQTT)
- ArduinoJson
- Docker / Docker Compose
- Node.js + Node-RED
- Mosquitto MQTT Broker
- Azure VM Linux - Almalinux

---

## **MQTT - Broker e Tópico**

- **Broker:** `mqtt://104.41.50.45:1880:1883`
- **Tópico de publicação:** `mottu/moto01/status`
- **QoS:** 0 (garantia de entrega)

---

## 🔹 **Como Executar o Projeto**

### 1. Clonar o repositório

```bash
git clone https://github.com/Entrega-CheckPoint/IOT-IOB-GENERATIVE-IA-SPRINT01
```

### 2. Subir os containers na Azure

```bash
cd challenge-mottu-iot

sudo yum update -y 

sudo yum install -y docker docker-compose-plugin

sudo docker compose up -d
```

### 3. Configurar o ESP32 (Arduino IDE)

- Editar `main.cpp` com:
  - SSID: `rede wifi`
  - BROKER_MQTT: 104.41.50.45:1880
  - TOPICO_PUBLISH: `mottu/moto01/status`

### 4. Visualizar no Node-RED

- Acesse `http://http://104.41.50.45:1880`
- Veja os dados chegando no tópico configurado com `mqtt in`

---

## **Exemplo de JSON Publicado**

```json
{
  "ID": "mosquitto",
  "Sensor": "ESP32-TESTE",
  "IP": "192.168.188.18",
  "MAC": "24:0A:C4:00:01:10",
  "RSSI": -57
}
```

---

## Link para o vídeo

> \[Link para o vídeo no YouTube - não listado]
