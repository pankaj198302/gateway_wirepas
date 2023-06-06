# Adding Systemd to the WP76 Image
Reference:https://wiki.koansoftware.com/index.php/Add_a_systemd_service_file_into_a_Yocto_image#:~:text=Add%20the%20following%20lines%20to%20the%20local.conf%20to,%2B%3D%20%22sysvinit%22%20VIRTUAL-RUNTIME_init_manager%20%3D%20%22systemd%22%20VIRTUAL-RUNTIME_initscripts%20%3D%20%22systemd-compat-units%22
## Add the below lines to your local.conf: 
DISTRO_FEATURES_append = " systemd"

DISTRO_FEATURES_BACKFILL_CONSIDERED += "sysvinit"

Generate the .cwe file and flash it to the device.



