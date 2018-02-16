BOOT_IMG ?= boot.png
FASTBOOT_IMG ?= fastboot.png

../splash.zip: ../out/splash.img
	cd ../out && zip -r ../splash.zip *

../out/splash.img: ../out/META-INF 720x1280_header.img ../tmp/boot.bgr ../tmp/fastboot.bgr
	cat 720x1280_header.img ../tmp/boot.bgr 720x1280_header.img ../tmp/fastboot.bgr > $@

../out/META-INF: ../out META-INF
	cp -R META-INF $@

../tmp/boot.bgr: ../tmp boot.png
	convert $(BOOT_IMG) -channel bgr -depth 8 $@

../tmp/fastboot.bgr: ../tmp fastboot.orig.png
	convert $(FASTBOOT_IMG) -channel bgr -depth 8 $@

../out:
	mkdir -p $@

../tmp:
	mkdir -p $@/pkg
