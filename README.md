# zmk-presentation-pointer

ZMK config for a 3-key presentation clicker with an MPU6050 air-mouse pointer,
running on a nice!nano (pro-micro footprint).

- The `clicker` shield (this repo, `boards/shields/clicker`) provides three direct-wired
  keys on pro-micro pins D7/D8/D9: **Right**, **momentary layer 1**, **Left**.
- The [`air_mouse` add-on shield](https://github.com/EyalYe/zmk-gyro-pointer) layers a
  gyro-driven mouse pointer on top: while layer 1 is held, tilting the remote moves the
  cursor. The MPU6050 is wired to I2C on D2 (SDA) / D3 (SCL).

GitHub Actions builds `clicker air_mouse` firmware on every push (see `build.yaml`);
grab `zmk.uf2` from the workflow artifacts and flash it via the nice!nano bootloader.
