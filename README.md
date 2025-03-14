# Zest_Sensor_IMU

Zest_Sensor_IMU board support for Zephyr OS.

## Usage

This board enables the following components:

- [Bosch BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/) humidity sensor,
- [Bosch BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/) smart IMU,
- [ST IIS2DLPC](https://www.st.com/en/mems-and-sensors/iis2dlpc.html) motion sensor.

:bulb: This driver should also be added to your workspace:

- [Bosch BNO055 driver](https://github.com/catie-aq/zephyr_bosch-bno055) for Zephyr OS

:pushpin: This shield defines:

- a humidity sensor device: `bme280_zest_sensor_imu_<port>`,
- a smart imu device: `bno055_zest_sensor_imu_<port>`,
- a motion sensor device: `iis2dlpc_zest_sensor_imu_<port>`.

:triangular_ruler: To use this shield:

- Update your device tree by adding the `ZEST_SENSOR_IMU(port)` macro to the `app.overlay` file.\
  Replace `port` with the number of the Zest_Core port to which the shield is connected, e.g.:

  ```c
  ZEST_SENSOR_IMU(1) /* Zest_Sensor_IMU connected to Zest_Core first port */
  ```

- Activate support for the shield by adding `--shield zest_sensor_imu` to the west command.

## Advanced Usage

This shield can be hardware-modified to suit your application.

In that case, use instead the alternate variant of the shield:

- Update your device tree by adding the `ZEST_SENSOR_IMU_ALT(port, irq)` macro to the `app.overlay` file, with:
  - `port`: number of the Zest_Core port to which the shield is connected,
  - `irq`: smart imu IRQ pin
- Activate support for the shield by adding `--shield zest_sensor_imu_alt` to the west command.
