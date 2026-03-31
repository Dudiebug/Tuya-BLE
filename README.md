# Tuya BLE

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/integration)

A Home Assistant custom integration for Tuya BLE (Bluetooth Low Energy) devices.

> **This fork** ([dudiebug/Tuya-BLE](https://github.com/Dudiebug/Tuya-BLE)) adds support for the **Evanshow Z02 smart doorknob** and includes a bug fix that prevents a `BleakNotFoundError` from crashing the integration entry setup when a BLE device is out of range at HA startup. HA now retries in the background via `ConfigEntryNotReady` until the device comes back in range.

---

## Supported devices

| Category | Device |
|----------|--------|
| Smart Lock (`ms`) | Smart Lock |
| Smart Lock Pro (`jtmspro`) | Gimdow A1 PRO MAX |
| Smart Lock Pro (`jtmspro`) | **Evanshow Z02** (doorknob) |
| Fingerbot (`szjqr`) | Fingerbot |
| Fingerbot (`szjqr`) | Fingerbot Plus |
| Fingerbot (`szjqr`) | CUBETOUCH 1s |
| Fingerbot (`szjqr`) | CubeTouch II |
| Thermostatic Radiator Valve (`wk`) | Thermostatic Radiator Valve |
| CO₂ Detector (`co2bj`) | CO₂ Detector |
| Temperature / Humidity (`wsdcg`) | Temperature Humidity Sensor |
| Temperature / Humidity (`wsdcg`) | Soil Moisture Sensor |
| Smart Water Bottle (`znhsb`) | Smart Water Bottle |
| Irrigation (`ggq`) | Irrigation Computer |

---

## Requirements

- Home Assistant 2023.1.0 or newer
- [HACS](https://hacs.xyz/) (for easy installation)
- Your Tuya device credentials (Device ID and Local Key) — obtainable via the [Tuya IoT Platform](https://iot.tuya.com/) or community tools

---

## Installation via HACS

1. Open **HACS → Integrations → ⋮ → Custom repositories**
2. Enter the URL `https://github.com/Dudiebug/Tuya-BLE` and set the category to **Integration** → click **Add**
3. Search for **Tuya Local BLE**, install it, then restart Home Assistant

## Manual installation

1. Copy the `custom_components/tuya_local_ble` folder into your HA `config/custom_components/` directory
2. Restart Home Assistant

---

## Configuration

After restarting, go to **Settings → Devices & Services → Add Integration** and search for **Tuya Local BLE**. Follow the prompts to enter your device credentials.

---

## Credits

Original integration by [@ShonP40](https://github.com/ShonP40) and contributors — full credit and original license preserved, see [LICENSE](LICENSE).

Inspired by and derived from:
- [@PlusPlus-ua](https://github.com/PlusPlus-ua/ha_tuya_ble)
- [@redphx](https://github.com/redphx/poc-tuya-ble-fingerbot)
- [@SupaHotMoj0](https://github.com/SupaHotMoj0/tuya_ble)
- [@dmickeyus](https://github.com/dmickeyus)
