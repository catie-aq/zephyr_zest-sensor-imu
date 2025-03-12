# Zest_Sensor_IMU

Zest_Sensor_IMU board support for Zephyr OS.

## Usage

This board enables the following components:

- [Bosch BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/) humidity sensor
- [Bosch BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/) smart IMU
- [ST IIS2DLPC](https://www.st.com/en/mems-and-sensors/iis2dlpc.html) motion sensor

:bulb: This driver should also be added to your workspace:

- [Bosch BNO055 driver](https://github.com/catie-aq/zephyr_bosch-bno055) for Zephyr-OS

> [!NOTE]
> The node label for the BME280 component is `bme280_zest_sensor_imu`. \
> The node label for the BNO055 component is `bno055_zest_sensor_imu`. \
> The node label for the IIS2DLPC component is `iis2dlpc_zest_sensor_imu`. \
> Shield name: `zest_sensor_imu`.
