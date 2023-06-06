# Adding Systemd to the WP76 Image
Reference:https://wiki.koansoftware.com/index.php/Add_a_systemd_service_file_into_a_Yocto_image#:~:text=Add%20the%20following%20lines%20to%20the%20local.conf%20to,%2B%3D%20%22sysvinit%22%20VIRTUAL-RUNTIME_init_manager%20%3D%20%22systemd%22%20VIRTUAL-RUNTIME_initscripts%20%3D%20%22systemd-compat-units%22
## Add the below lines to your local.conf: 
DISTRO_FEATURES_append = " systemd"

DISTRO_FEATURES_BACKFILL_CONSIDERED += "sysvinit"

Generate the .cwe file and flash it to the device. Check the systemd available in the image with bitbake -e mdm9x28-image-minimal | grep ^DISTRO_FEATURES=

You should get a response as below where we can see the systemd included in the image: 

bitbake -e mdm9x28-image-minimal | grep ^DISTRO_FEATURES=
DISTRO_FEATURES="argp ext2 irda largefile usbgadget usbhost wifi xattr nfs 3g nfc ipv4 ipv6 libc-backtrace libc-big-macros libc-bsd libc-cxx-tests libc-catgets libc-charsets libc-crypt 			libc-crypt-ufc libc-db-aliases libc-envz libc-fcvt libc-fmtmsg libc-fstab libc-ftraverse 					libc-getlogin libc-idn libc-inet-anl libc-libm libc-locales libc-locale-code 					libc-memusage libc-nis libc-nsswitch libc-rcmd libc-rtld-debug libc-spawn libc-streams libc-sunrpc 					libc-utmp libc-utmpx libc-wordexp libc-posix-clang-wchar libc-posix-regexp libc-posix-regexp-glibc 					libc-posix-wchar-io largefile multiarch systemd pulseaudio bluez5 gobject-introspection-data ldconfig"




