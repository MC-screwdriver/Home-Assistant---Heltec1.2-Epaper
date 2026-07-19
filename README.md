# ESPHome Heltec Wireless Paper V1.2 E-Paper Driver

ESPHome External Component für das **Heltec Wireless Paper V1.2** mit dem integrierten
2,13"-E-Paper-Display **E0213A367-BW**.

## Status

**Entwicklungsstand:** `v0.3.0-dev`

Getestet mit:
- Heltec Wireless Paper V1.2
- ESP32-S3
- ESPHome 2026.7.0
- Arduino Framework

## Installation

```yaml
external_components:
  - source:
      type: git
      url: https://github.com/MC-screwdriver/Home-Assistant---Heltec1.2-Epaper
      ref: main
    components:
      - heltec_epaper
```

## Pinbelegung

| Funktion | GPIO |
|----------|------|
| CLK | GPIO3 |
| MOSI | GPIO2 |
| CS | GPIO4 |
| DC | GPIO5 |
| RESET | GPIO6 |
| BUSY | GPIO7 |
| VEXT | GPIO45 |

## Hinweise

- Partial Refresh: ca. 853–855 ms
- Full Refresh: ca. 1755–1757 ms
- `GPIO3` und `GPIO45` sind Strapping-Pins und erzeugen in ESPHome Warnungen.
- Nicht gleichzeitig `update_interval` **und** `component.update` mit gleichem Intervall verwenden.

## Projektstruktur

```
components/
└── heltec_epaper/
    ├── __init__.py
    ├── display.py
    ├── heltec_epaper.cpp
    └── heltec_epaper.h
```

## Roadmap

- v0.3 Treiber aufräumen
- GitHub-Dokumentation
- Beispiele
- Deep-Sleep-Unterstützung
- Weitere Heltec-Displays
