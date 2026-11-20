# Stand-in "kernel source" for the prebuilt Kleaf 6.6 kernel.
# MikuUI only needs two things from TARGET_KERNEL_SOURCE when the kernel is
# prebuilt: the version fields below (vendor/miku/config/BoardConfigKernel.mk)
# and `make headers_install` (generated_kernel_includes in
# vendor/miku/build/soong/Android.bp). headers_install unpacks the UAPI header
# tarball produced by the same Kleaf build into $(O)/usr/include.
VERSION = 6
PATCHLEVEL = 6
SUBLEVEL = 144
EXTRAVERSION =

HEADERS_TARBALL := $(CURDIR)/../kernel-uapi-headers.tar.gz

.PHONY: headers_install kernelversion
headers_install:
	@mkdir -p $(O)
	@gzip -d < $(HEADERS_TARBALL) | tar -x -C $(O)

kernelversion:
	@echo $(VERSION).$(PATCHLEVEL).$(SUBLEVEL)
