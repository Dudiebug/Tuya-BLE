# Tuya BLE — Evanshow Z02 Fork

A fork of [ShonP40/Tuya-BLE](https://github.com/ShonP40/Tuya-BLE) edited with [Claude Code](https://claude.ai/code) to add support for the **Evanshow Z02 smart lock** (`jtmspro` / product ID `n1qxwwic`).

All original device support is preserved. The only addition is the Z02.

---

## What's added

| Entity | Type | DP | Notes |
|---|---|---|---|
| Lock | `lock` | 47 (state), 46 (lock), 19 (BLE unlock) | Main lock/unlock control |
| Automatic Lock | `switch` | 33 | Enable/disable auto-lock |
| Beep Volume | `select` | 31 | mute / low / normal / high |
| Battery State | `sensor` | 9 | high / normal / low / poweroff |
| Alarm Lock | `sensor` | 21 | Diagnostic — alarm type |
| Unlock triggers | `binary_sensor` | 12, 13, 15, 19, 55, 62, 63 | Diagnostic, disabled by default — fingerprint / password / card / BLE / temporary / phone remote / voice remote |

---

## Installation via HACS

1. **HACS → Integrations → ⋮ → Custom repositories**
2. URL: `https://github.com/Dudiebug/Tuya-BLE` — category: **Integration** → **Add**
3. Search for **Tuya Local BLE** → Install → Restart HA

---

## Configuration

Create `config/tuya_local_ble/devices.json`:

```json
{
  "DC:23:52:XX:XX:XX": {
    "address": "DC:23:52:XX:XX:XX",
    "uuid": "<device UUID>",
    "local_key": "<local key>",
    "device_id": "<device ID>",
    "category": "jtmspro",
    "product_id": "n1qxwwic",
    "device_name": "Front Door",
    "product_model": "Z02",
    "product_name": "Smart lock"
  }
}
```

Obtain credentials with [TinyTuya](https://github.com/jasonacox/tinytuya).

---

## Credits

Original integration by [@ShonP40](https://github.com/ShonP40) and contributors. Full credit and original license preserved — see [LICENSE](LICENSE).

Inspired by and derived from:
- [@PlusPlus-ua](https://github.com/PlusPlus-ua/ha_tuya_ble)
- [@redphx](https://github.com/redphx/poc-tuya-ble-fingerbot)
- [@SupaHotMoj0](https://github.com/SupaHotMoj0/tuya_ble)
- [@dmickeyus](https://github.com/dmickeyus)
