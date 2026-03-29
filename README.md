# Tuya BLE — dudiebug fork

A fork of [ShonP40/Tuya-BLE](https://github.com/ShonP40/Tuya-BLE) with a bug fix for Home Assistant startup stability.

---

## What's changed

**Fix: BLE device unavailable at startup no longer blocks HA boot**

`async_setup_entry` now wraps `device.update()` in a `try/except` that raises `ConfigEntryNotReady` when the device is unreachable, instead of propagating a `BleakNotFoundError` that crashed the entry setup. HA will now retry the integration in the background once the device comes back in range.

---

## Installation via HACS

1. **HACS → Integrations → ⋮ → Custom repositories**
2. URL: `https://github.com/Dudiebug/Tuya-BLE` — category: **Integration** → **Add**
3. Search for **Tuya Local BLE** → Install → Restart HA

---

## Credits

Original integration by [@ShonP40](https://github.com/ShonP40) and contributors. Full credit and original license preserved — see [LICENSE](LICENSE).

Inspired by and derived from:
- [@PlusPlus-ua](https://github.com/PlusPlus-ua/ha_tuya_ble)
- [@redphx](https://github.com/redphx/poc-tuya-ble-fingerbot)
- [@SupaHotMoj0](https://github.com/SupaHotMoj0/tuya_ble)
- [@dmickeyus](https://github.com/dmickeyus)
