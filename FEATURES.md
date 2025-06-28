# RTL Canary 25.02 Highlights

The `rtlcanary` directory tracks rtl_433 release **25.02 (2025‑02‑19)**. Compared
with the 24.10 version used by the Marco plugin, the major additions include:

- General Motors TPMS support.
- Globe Thermometer option for Bresser 8‑in‑1 sensors.
- Rain start detection for WS90 sensors.
- New `id` key for IDM and NETIDM devices.
- Configuration for Hormann remotes and Rako lighting controls.
- Optional client certificate in the Home Assistant script.
- Support for the Revolt ZX‑7717 power meter.
- Gridstream RF protocol support for Landis & Gyr meters.
- Quinetic switches and sensors decoder.
- Numerous other device decoders such as DeltaDore X3D, ST1005H thermometers,
  Thermopro TP828B, and Arexx TL‑3TSN.

In addition to new devices, the release introduces MQTT reconnect throttling,
OpenMetrics/Prometheus API support, and several decoder improvements and bug
fixes.
