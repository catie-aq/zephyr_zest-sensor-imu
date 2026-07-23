# Zest_Sensor_IMU

Zest_Sensor_IMU board support for Zephyr OS.

## Version 1.0.2

### Components

- [Bosch BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/) humidity sensor,
- [Bosch BMA280](https://www.bosch-sensortec.com/products/motion-sensors/accelerometers/bma280.html) triaxial acceleration sensor,
- [Bosch BMG160](https://www.bosch-sensortec.com/bst/products/all_products/bmg160) gyroscope,
- [NXP FXAS21002](https://www.nxp.com/products/sensors/motion-sensors/3-axis-digital-angular-rate-gyroscope:FXAS21002C) gyroscope,
- [Bosch BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/) smart IMU.

:bulb: This driver should also be added to your workspace:

- [Bosch BNO055 driver](https://github.com/catie-aq/zephyr_bosch-bno055) for Zephyr OS.

### Devices

- `bme280_zest_sensor_imu_<port>` humidity sensor,
- `bma280_zest_sensor_imu_<port>` triaxial acceleration sensor,
- `bmg160_zest_sensor_imu_<port>` gyroscope,
- `fxas21002_zest_sensor_imu_<port>` gyroscope,
- `bno055_zest_sensor_imu_<port>` smart IMU.

### Standard Variant

- Update your device tree by adding the `ZEST_SENSOR_IMU(port)` macro to the `app.overlay` file.\
  Replace `port` with the number of the Zest_Core port to which the shield is connected, for example:

  ```dts
  ZEST_SENSOR_IMU(1) /* Zest_Sensor_IMU connected to Zest_Core first port */
  ```

- Activate support for the shield by adding `--shield zest_sensor_imu` to the west command.

### Alternate Variant

- Update your device tree by adding the `ZEST_SENSOR_IMU_ALT(port, irq)` macro to the `app.overlay` file, with:
  - `port`: number of the Zest_Core port to which the shield is connected,
  - `irq`: smart IMU IRQ pin (cf. [6tron connector](https://github.com/catie-aq/zephyr_6tron-connector/blob/main/dts/bindings/sixtron-bus.yaml)).

  ```dts
  ZEST_SENSOR_IMU_ALT(1, WKUP) /* Configured with IRQ pin WKUP for IMU */
  ```

- Activate support for the shield by adding `--shield zest_sensor_imu_alt` to the west command.

## Version 4.0.0

### Components

- [ST ISM330DHCX](https://www.st.com/en/mems-and-sensors/ism330dhcx.html) 6-axis IMU,
- [ST IIS2MDC](https://www.st.com/en/mems-and-sensors/iis2mdc.html) magnetometer (disabled by default in the DTS overlay).

### Devices

- `ism330dhcx_zest_sensor_imu_<port>` IMU,
- `iis2mdc_zest_sensor_imu_<port>` magnetometer.

### Standard Variant

- Update your device tree by adding the `ZEST_SENSOR_IMU(port)` macro to the `app.overlay` file.\
  Replace `port` with the number of the Zest_Core port to which the shield is connected, for example:

  ```dts
  ZEST_SENSOR_IMU(1) /* Zest_Sensor_IMU connected to Zest_Core first port */
  ```

- Activate support for the shield by adding `--shield zest_sensor_imu_4.0.0` to the west command.

### Alternate Variant

- Update your device tree by adding the `ZEST_SENSOR_IMU_ALT(port, ism330dhcx_irq, iis2mdc_irq)` macro to the `app.overlay` file, with:
  - `port`: number of the Zest_Core port to which the shield is connected,
  - `ism330dhcx_irq`: IMU IRQ pin,
  - `iis2mdc_irq`: magnetometer IRQ pin
    (cf. [6tron connector](https://github.com/catie-aq/zephyr_6tron-connector/blob/main/dts/bindings/sixtron-bus.yaml)).

  ```dts
  ZEST_SENSOR_IMU_ALT(1, DIO1, DIO3) /* Configured with IRQ pins DIO1 for IMU and DIO3 for magnetometer */
  ```

- Activate support for the shield by adding `--shield zest_sensor_imu_4_0_0_alt` to the west command.
