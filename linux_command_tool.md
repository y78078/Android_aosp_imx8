# linux_command_tool
## ENV nxp imx8qmmek Android Automotive 12.0.0_2.1.0 (Linux 5.15.32 BSP)

## get vehicle property
VENDOR_TIME_SET_HOUR=$(dumpsys car_service get-property-value 561033488 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_MIN=$(dumpsys car_service get-property-value 561033489 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_SEC=$(dumpsys car_service get-property-value 561033490 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_DATE=$(dumpsys car_service get-property-value 561033491 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_MONTH=$(dumpsys car_service get-property-value 561033492 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_DAY=$(dumpsys car_service get-property-value 561033493 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)
 
date "2022-11-12 13:14:15"






grep -irs vendor.vehicle.event

vendor/nxp-opensource/imx/evs/evs_service/evs_service.cpp:#define RPMSG_CAN_EVENT  "vendor.vehicle.event"
device/nxp/imx8q/sepolicy_car/property_contexts:vendor.vehicle.event      u:object_r:vendor_evs_prop:s0
device/nxp/imx8q/mek_8q/init_car.rc:on property:vendor.vehicle.event=1 && property:vendor.evs.video.ready=1
device/nxp/imx8q/mek_8q/init_car.rc:on property:vendor.vehicle.event=0
