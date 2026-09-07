# Esphome-config

ESPHome device configs for Home Assistant.

Managed via the **ESPHome Home Assistant add-on** (configs live in the add-on's
`/config/esphome` directory).

## Layout

```
config/
  atom_echo.yaml        # M5Stack Atom Echo node
  secrets.example.yaml  # template — copy to secrets.yaml + fill in
  secrets.yaml          # REAL secrets — DO NOT COMMIT (gitignored)
LICENSE
```

## Getting started

1. Copy `config/secrets.example.yaml` → `config/secrets.yaml` and fill in real
   values (Wi-Fi SSID/password, API encryption key, OTA password).
   > In the ESPHome add-on, add secrets via **Configuration → Files**
   > (editing `/config/esphome/secrets.yaml`), or drop the inline-style keys
   > above into a local `secrets.yaml`.
2. Per-node files are referenced by their device config — e.g. `atom_echo.yaml`
   pulls `!secret` values from `secrets.yaml`.
3. Add the node in the ESPHome add-on dashboard and compile/install.

## Adding a new device

- Drop a new `config/<device>.yaml`
- Reuse the `!secret` pattern so no credentials live in committed config
- Verify hardware (board, pins) against the ESPHome docs before flashing

## License

FUCK YOUR LICENSE. See `LICENSE`.