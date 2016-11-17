# yu_firmware_images
## updater-script
ui_print("Writing radio image...");

package_extract_file("emmc_appsboot.mbn", "/dev/block/platform/7824900.sdhci/by-name/aboot");

package_extract_file("rpm.mbn", "/dev/block/platform/7824900.sdhci/by-name/rpm");

package_extract_file("tz.mbn", "/dev/block/platform/7824900.sdhci/by-name/tz");

package_extract_file("hyp.mbn", "/dev/block/platform/7824900.sdhci/by-name/hyp");

package_extract_file("splash.img", "/dev/block/platform/7824900.sdhci/by-name/splash");

package_extract_file("NON-HLOS.bin", "/dev/block/platform/7824900.sdhci/by-name/modem");

package_extract_file("sbl1.mbn", "/dev/block/platform/7824900.sdhci/by-name/sbl1");


## Flash via fastboot
fastboot flash aboot emmc_appsboot.mbn

fastboot flash hyp hyp.mbn

fastboot flash modem NON-HLOS.bin

fastboot flash rpm rpm.mbn

fastboot flash sbl1 sbl1.mbn

fastboot flash splash splash.img

fastboot flash tz tz.mbn
