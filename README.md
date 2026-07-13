# zmk-presentation-pointer

ZMK config for a 3-key presentation clicker with an MPU6050 air-mouse pointer,
running on a nice!nano (pro-micro footprint).

- The `clicker` shield (this repo, `boards/shields/clicker`) provides three direct-wired keys.
- The [`air_mouse` add-on shield](https://github.com/EyalYe/zmk-gyro-pointer) layers a
  gyro-driven mouse pointer on top: while the middle key (layer 1) is held, tilting the
  remote moves the cursor.

## Wiring

| Function | Pro-micro pin | nRF GPIO |
|---|---|---|
| Key: **Right**                 | D7 | P0.11 |
| Key: **layer 1** (hold to move the mouse) | D8 | P1.04 |
| Key: **Left**                  | D9 | P1.06 |
| MPU6050 **SDA**                | D2 | P0.17 |
| MPU6050 **SCL**                | D3 | P0.20 |

Keys switch to ground (internal pull-ups); the MPU6050 runs off 3.3 V and GND.

GitHub Actions builds `clicker air_mouse` firmware on every push (see `build.yaml`);
grab `zmk.uf2` from the workflow artifacts and flash it via the nice!nano bootloader.
