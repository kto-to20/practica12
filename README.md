# Multi-Protocol IoT Gateway (MQTT + Zigbee) using OpenHAB

## Project Description

This project demonstrates the implementation of a **Multi-protocol IoT Gateway** using **OpenHAB** as a central hub.
The system integrates **MQTT sensors** and **Zigbee devices** and provides a unified interface for monitoring and automation.

The gateway allows communication between different IoT protocols and enables cross-protocol automation through OpenHAB Rules.

## System Architecture

```mermaid
graph TD

A[MQTT Sensors] -->|MQTT Protocol| B(OpenHAB Gateway)

B --> C[Zigbee Devices]

B --> D[Automation Rules Engine]

B --> E[REST API]

B --> F[Unified Dashboard]
```

## Components

### MQTT Sensors (Simulated)

The system includes three virtual MQTT sensors:

* Temperature sensor
* Humidity sensor
* Light sensor

Sensor data is simulated using OpenHAB rules to demonstrate system behavior.

### Zigbee Devices

The gateway controls several simulated Zigbee devices:

* Zigbee Light
* Zigbee Fan
* Zigbee Socket

These devices can be controlled manually through the dashboard or automatically through rules.

## Cross-Protocol Automation

Automation rules connect MQTT sensor data with Zigbee device actions.

Examples:

* If **temperature > 25°C → turn ON Zigbee Fan**
* If **light level < 100 lx → turn ON Zigbee Light**

This demonstrates interoperability between different IoT protocols.

## OpenHAB Configuration Files

The project includes the following configuration files:

```
items/
iot_devices.items

things/
mqtt_zigbee.things

rules/
bridge.rules

sitemaps/
iot_dashboard.sitemap
```

## Dashboard

Unified dashboard for monitoring sensors and controlling devices.

Dashboard URL:

```
http://localhost:8080/basicui/app?sitemap=iot_dashboard
```

## Installation and Setup

1. Install **OpenHAB 4.x**
2. Install required bindings:

   * MQTT Binding
   * Zigbee Binding
   * JSONPATH Transformation
   * MAP Transformation
3. Copy configuration files to OpenHAB `conf` directory:

```
conf/items
conf/things
conf/rules
conf/sitemaps
```

4. Restart OpenHAB or wait for automatic reload.

## Demo

The system demonstrates:

* multi-protocol integration
* cross-protocol automation
* centralized monitoring
* unified IoT dashboard

Sensor values are simulated using OpenHAB rules to emulate real IoT devices.

---

# Багатопротокольний IoT шлюз (MQTT + Zigbee) з використанням OpenHAB

## Опис проєкту

Даний проєкт демонструє реалізацію **багатопротокольного IoT шлюзу** з використанням **OpenHAB** як центрального хабу.
Система інтегрує **MQTT сенсори** та **Zigbee пристрої** і надає єдиний інтерфейс для моніторингу та керування.

Шлюз забезпечує взаємодію між різними IoT протоколами та реалізує автоматизацію через **OpenHAB Rules**.

## Архітектура системи

```mermaid
graph TD

A[MQTT сенсори] -->|MQTT протокол| B(OpenHAB шлюз)

B --> C[Zigbee пристрої]

B --> D[Модуль автоматизації]

B --> E[REST API]

B --> F[Єдина панель керування]
```

## Компоненти системи

### MQTT сенсори (емуляція)

У системі використовується три віртуальні сенсори:

* сенсор температури
* сенсор вологості
* сенсор освітлення

Для демонстрації роботи системи значення сенсорів генеруються через **OpenHAB Rules**.

### Zigbee пристрої

Шлюз керує кількома Zigbee пристроями:

* Zigbee лампа
* Zigbee вентилятор
* Zigbee розетка

Пристрої можуть керуватись як вручну через dashboard, так і автоматично через правила.

## Міжпротокольна автоматизація

Автоматизація пов’язує дані MQTT сенсорів із діями Zigbee пристроїв.

Приклади:

* якщо **температура > 25°C → вмикається Zigbee вентилятор**
* якщо **рівень освітлення < 100 lx → вмикається Zigbee лампа**

Це демонструє **інтероперабельність між різними IoT протоколами**.

## Конфігураційні файли OpenHAB

Проєкт містить такі файли:

```
items/
iot_devices.items

things/
mqtt_zigbee.things

rules/
bridge.rules

sitemaps/
iot_dashboard.sitemap
```

## Dashboard

Система має єдину панель керування для:

* перегляду даних сенсорів
* моніторингу стану пристроїв
* ручного керування пристроями

Адреса dashboard:

```
http://localhost:8080/basicui/app?sitemap=iot_dashboard
```

## Встановлення та запуск

1. Встановити **OpenHAB 4.x**
2. Встановити необхідні bindings:

   * MQTT Binding
   * Zigbee Binding
   * JSONPATH Transformation
   * MAP Transformation
3. Скопіювати конфігураційні файли у папку `conf`:

```
conf/items
conf/things
conf/rules
conf/sitemaps
```

4. Перезапустити OpenHAB або дочекатися автоматичного перезавантаження конфігурації.

## Демонстрація

Система демонструє:

* інтеграцію кількох IoT протоколів
* міжпротокольну автоматизацію
* централізований моніторинг
* єдину панель керування IoT системою

Значення сенсорів симулюються через правила OpenHAB для демонстрації роботи системи.
