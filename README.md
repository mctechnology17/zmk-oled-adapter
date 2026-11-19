<!-- mc-follow-top:start -->
<div align="center">

  <a href="https://youtube.com/@mctechnology17">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github.com/mctechnology17/mctechnology17/blob/main/src/mctechnology_banner_dark.png?raw=true" />
      <img alt="MC Technology" width="420px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/mctechnology_banner_light.png?raw=true" />
    </picture>
  </a>
  <br>
  <a href="https://youtube.com/@mctechnology17"><img align="center" alt="MC Technology | YouTube" width="22px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/youtube.png" /></a>
  <a href="https://www.instagram.com/mctechnology17/"><img align="center" alt="MC Technology | Instagram" width="22px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/instagram.png" /></a>
  <a href="https://www.facebook.com/mctechnology17/"><img align="center" alt="MC Technology | Facebook" width="22px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/facebook.png" /></a>
  <a href="https://www.tiktok.com/@mctechnology17"><img align="center" alt="MC Technology | TikTok" width="22px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/tiktok.png" /></a>
  <a href="https://t.me/mctechnology17"><img align="center" alt="MC Technology | Telegram" width="22px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/telegram.png" /></a>
  <a href="https://discord.gg/7zs2fezBbv"><img align="center" alt="MC Technology | Discord" width="22px" src="https://github.com/mctechnology17/mctechnology17/blob/main/src/discord.png" /></a>

</div>
<!-- mc-follow-top:end -->

# Oled Adapter
This module is an adapter for 128x32, 128x64 and 128x128 OLED screens, to be
used on keyboards with ZMK without having to modify the shields of the
keyboards.

Compatible with all boards with pro micro and seeeduino xiao BLE pinout, like
the Nice!Nano, Puchi, clones and others.

Shields supported:
- oled_adapter_pro_micro_128x32
- oled_adapter_pro_micro_128x64
- oled_adapter_pro_micro_128x128
- oled_adapter_seeeduino_xiao_ble_128x32
- oled_adapter_seeeduino_xiao_ble_128x64
- oled_adapter_seeeduino_xiao_ble_128x128

[![oled_adapter_example1](src/oled_adapter_example1.jpg)](https://github.com/mctechnology17/zmk-config)
[![oled_adapter_example2](src/oled_adapter_example2.jpg)](https://github.com/mctechnology17/zmk-config)

# Usage
The following commands demonstrate how to overwrite the default 128x32 screen
with different screen sizes for various setups as an example:

- **Overwrite the left screen from 128x32 to 128x128:**
  ```bash
  west build -b nice_nano_v2 -- -DSHIELD="corne_left oled_adapter_pro_micro_128x128"
  ```

- **Overwrite the right screen from 128x32 to 128x64:**
  ```bash
  west build -b puchi_ble_v1 -- -DSHIELD="corne_right oled_adapter_pro_micro_128x64"
  ```

- **Using the Xiao as a dongle with the Corne, replacing the screen with 128x128:**
  ```bash
  # This example is from a dongle previously configured using a corne
  west build -b seeeduino_xiao_ble -- -DSHIELD="corne_dongle_xiao dongle_display oled_adapter_seeeduino_xiao_ble_128x128"
  ```

# Configuration
To use this module, first add it to your `config/west.yml` by adding a new
entry to `remotes` and `projects`:

```yaml
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: mctechnology17
      url-base: https://github.com/mctechnology17
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: zmk-oled-adapter
      remote: mctechnology17
      revision: main
  self:
    path: config
```

Now simply indicate in the board and the shield in the `build.yaml` file:

```yaml
---
include:
  - board: nice_nano_v2
    shield: corne_left oled_adapter_pro_micro_128x128
  - board: puchi_ble_v1
    shield: corne_right oled_adapter_pro_micro_128x64
```

<!-- mc-follow:start -->
# Support this project

This is a personal project that I build in my free time. If it is useful to
you, the best way to help is to follow and subscribe:

[YouTube](https://youtube.com/@mctechnology17) · [Instagram](https://www.instagram.com/mctechnology17/) · [Facebook](https://www.facebook.com/mctechnology17/) · [TikTok](https://www.tiktok.com/@mctechnology17)

News and community: [Telegram](https://t.me/mctechnology17) · [Discord](https://discord.gg/7zs2fezBbv)

I make videos about split keyboards, ZMK and open source (in Spanish, long
videos with English subtitles). Every follow and every subscription helps me a
lot and keeps me motivated to bring more to the open source community.

Thank you for every report and every issue: they make these projects better.
<!-- mc-follow:end -->
