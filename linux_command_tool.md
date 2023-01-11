# linux_command_tool
## ENV nxp imx8qmmek Android Automotive 12.0.0_2.1.0 (Linux 5.15.32 BSP)

## get vehicle property
VENDOR_TIME_SET_HOUR=$(dumpsys car_service get-property-value 561033488 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_MIN=$(dumpsys car_service get-property-value 561033489 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_SEC=$(dumpsys car_service get-property-value 561033490 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_DATE=$(dumpsys car_service get-property-value 561033491 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_MONTH=$(dumpsys car_service get-property-value 561033492 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)

VENDOR_TIME_SET_DAY=$(dumpsys car_service get-property-value 561033493 |cut -d , -f 6|cut -d [ -f 2 | cut -d ] -f 1)
 
