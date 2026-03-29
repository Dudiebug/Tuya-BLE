# Changelog

All notable changes to this fork are documented here.
This project follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) conventions.

---

## [Unreleased] — dudiebug fork

### Added

- **Evanshow Z02 smart lock** support under the `jtmspro` category (product ID `n1qxwwic`)
  - **Lock entity** (`lock.manual_lock`): lock/unlock via BLE using DP 47 (`lock_motor_state`) for state and DP 19 (`unlock_ble`) / DP 46 (`manual_lock`) for commands. Keep-alive NOP on DP 52.
  - **Switch** (`switch.automatic_lock`): toggle auto-lock on/off (DP 33).
  - **Select** (`select.beep_volume`): set beeper volume to mute / low / normal / high (DP 31).
  - **Binary sensors** (diagnostic, disabled by default): unlock method triggers for fingerprint (DP 12), password (DP 13), card (DP 15), BLE (DP 19), temporary password (DP 55), phone remote (DP 62), voice remote (DP 63).
  - **Sensors** (in `sensor.py` — see manual step in README): battery state (DP 9) and alarm lock (DP 21).

### Changed

- `README.md`: updated supported-devices table; added HACS custom-repository installation instructions for this fork.
- `hacs.json`: added `homeassistant` minimum version field (`2023.1.0`).
- `LICENSE`: added dudiebug as contributor for 2026 changes.

---

*Upstream changelog: see [ShonP40/Tuya-BLE](https://github.com/ShonP40/Tuya-BLE)*
