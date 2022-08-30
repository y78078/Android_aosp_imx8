# 
## device/nxp/imx8q/sepolicy_car/carservice_app.te

### scontext=u:r:carservice_app:s0 tcontext=u:object_r:system_data_file:s0:c512,c768 tclass=dir  denied { search } 
### scontext=u:r:carservice_app:s0 tcontext=u:object_r:user_profile_root_file:s0:c512,c768 tclass=dir  denied { search }
## device/nxp/imx8q/sepolicy/vold.te
### scontext=u:r:vold:s0 tcontext=u:object_r:dm_deivce:s0:c512,c768 tclass=blk_file  denied { ioctl }

## device/nxp/imx8q/sepolicy_car/vendor_init.te
### scontext=u:r:vendor_init:s0 tcontext=u:object_r:rootfs:s0:c512,c768 tclass=dir  denied { read } 

## system/sepolicy/public/ueventd.te
### scontext=u:r:ueventd:s0 tcontext=u:object_r:ueventd:s0:c512,c768 tclass=capability  denied { sys_nice } 

##
### [   29.128394] type=1400 audit(1659956919.052:40): avc: denied { search } for comm="com.android.car" name="0" dev="dm-4" ino=72939 scontext=u:r:carservice_app:s0 tcontext=u:object_r:system_data_file:s0:c512,c768 tclass=dir permissive=0
