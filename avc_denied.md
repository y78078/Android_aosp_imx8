# Kernel or system messages include deny message
## Use audit2allow tool to generate policy rule
### adb pull /sys/fs/selinux/policy
### adb logcat -b all -d | audit2allow -p policy
### Or
### adb logact –b all –d > avc.log
### audit2allow –p policy –i avc.log
## Example of input avc denial to audit2allow:
### type=1400 audit(0.0:2578): avc: denied { search } for comm=41646170744C61756E636820566D name="2007" dev="proc" ino=219
### Result
### #============= vendor_hal_perf_default ==============
### allow vendor_hal_perf_default system_server:dir search;
## Audit2allow is not AOSP provided, can get on Ubuntu by
### sudo apt-get install policycoreutils-python-utils
