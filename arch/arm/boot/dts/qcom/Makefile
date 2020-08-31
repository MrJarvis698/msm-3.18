ifeq ($(CONFIG_OF),y)

ifeq ($(CONFIG_MACH_XIAOMI_HYDROGEN),y)
dtb-$(CONFIG_ARCH_MSM8916) += hydrogen-msm8956-mtp.dtb \
	hydrogen-msm8956-v1.1-mtp.dtb \
	hydrogen-msm8976-mtp.dtb \
	hydrogen-msm8976-v1.1-mtp.dtb
else ifeq ($(CONFIG_MACH_XIAOMI_KENZO),y)
dtb-$(CONFIG_ARCH_MSM8916) += kenzo-msm8956-mtp.dtb
else
dtb-$(CONFIG_ARCH_MSM8916) += msm8976-sim.dtb \
	msm8976-rumi.dtb \
	msm8976-qrd-skun.dtb \
	msm8976-qrd-skun-evt2.dtb \
	msm8976-v1.1-qrd-skun-dvt.dtb \
	msm8976-cdp.dtb \
	msm8976-mtp.dtb \
	msm8976-rcm.dtb \
	msm8976-internal-codec-cdp.dtb \
	msm8976-polaris.dtb \
	apq8076-cdp.dtb \
	apq8076-mtp.dtb \
	msm8956-sim.dtb \
	msm8956-rumi.dtb \
	msm8956-cdp.dtb \
	msm8956-mtp.dtb \
	msm8956-internal-codec-cdp.dtb \
	apq8056-cdp.dtb \
	apq8056-mtp.dtb \
	msm8956-v1.1-mtp.dtb \
	msm8956-v1.1-cdp.dtb \
	msm8956-v1.1-qrd-skun.dtb \
	apq8056-v1.1-mtp.dtb \
	apq8056-v1.1-cdp.dtb \
	msm8976-v1.1-mtp.dtb \
	msm8976-v1.1-mtp-rome.dtb \
	msm8976-v1.1-cdp.dtb \
	msm8976-v1.1-rcm.dtb \
	apq8076-v1.1-mtp.dtb \
	apq8076-v1.1-cdp.dtb \
	apq8076-v1.1-mtp-rome.dtb
endif

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif

targets += dtbs
targets += $(addprefix ../, $(DTB_LIST))
endif

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(DTB_LIST))

clean-files := *.dtb
