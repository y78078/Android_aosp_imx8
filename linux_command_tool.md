# linux_command_tool
## ENV nxp imx8qmmek Android Automotive 12.0.0_2.1.0 (Linux 5.15.32 BSP)

## get vehicle property

#!/system/bin/sh
START_YEAR=2000

VENDOR_TIME_SET_HOUR=$(dumpsys car_service get-property-value 561033488 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_MIN=$(dumpsys car_service get-property-value 561033489 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_SEC=$(dumpsys car_service get-property-value 561033490 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_YEAR=$(expr $(dumpsys car_service get-property-value 561033491 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1) + $START_YEAR)

VENDOR_TIME_SET_MONTH=$(dumpsys car_service get-property-value 561033492 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_DAY=$(dumpsys car_service get-property-value 561033493 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)
 
date "2022-11-12 13:14:15"

echo $VENDOR_TIME_SET_HOUR
echo $VENDOR_TIME_SET_MIN
echo $VENDOR_TIME_SET_SEC
echo $VENDOR_TIME_SET_YEAR
echo $VENDOR_TIME_SET_MONTH
echo $VENDOR_TIME_SET_DAY





grep -irs vendor.vehicle.event

vendor/nxp-opensource/imx/evs/evs_service/evs_service.cpp:#define RPMSG_CAN_EVENT  "vendor.vehicle.event"
device/nxp/imx8q/sepolicy_car/property_contexts:vendor.vehicle.event      u:object_r:vendor_evs_prop:s0
device/nxp/imx8q/mek_8q/init_car.rc:on property:vendor.vehicle.event=1 && property:vendor.evs.video.ready=1
device/nxp/imx8q/mek_8q/init_car.rc:on property:vendor.vehicle.event=0


grep -irs VEHICLE_RPMSG_EVENT

vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	EXTCON_VEHICLE_RPMSG_EVENT,
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_dummy_hw.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	EXTCON_VEHICLE_RPMSG_EVENT,
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 1);
vendor/nxp-opensource/kernel_imx/drivers/mxc/vehicle/vehicle_rpmsg_m4.c:	extcon_set_state_sync(ev_edev, EXTCON_VEHICLE_RPMSG_EVENT, 0);

vendor/nxp-opensource/kernel_imx/drivers/extcon/extcon.c:	[EXTCON_VEHICLE_RPMSG_EVENT] = {
vendor/nxp-opensource/kernel_imx/drivers/extcon/extcon.c:		.id = EXTCON_VEHICLE_RPMSG_EVENT,
vendor/nxp-opensource/kernel_imx/drivers/extcon/extcon.c:		.name = "VEHICLE_RPMSG_EVENT",

vendor/nxp-opensource/kernel_imx/include/linux/extcon.h:#define EXTCON_VEHICLE_RPMSG_EVENT     59
vendor/nxp-opensource/imx/evs/evs_service/evs_service.cpp:        if (!strncmp(cp, "STATE=VEHICLE_RPMSG_EVENT=0", strlen("STATE=VEHICLE_RPMSG_EVENT=0"))) {
vendor/nxp-opensource/imx/evs/evs_service/evs_service.cpp:        } else if (!strncmp(cp, "STATE=VEHICLE_RPMSG_EVENT=1", strlen("STATE=VEHICLE_RPMSG_EVENT=1"))) {

