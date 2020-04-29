# SPDX-License-Identifier: GPL-2.0
#dtb-y +=  exynos8890-gracelte_eur_open_00.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_01.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_02.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_03.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_05.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_07.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_09.dtb
#dtb-y +=  exynos8890-gracelte_eur_open_11.dtb

dtb-$(CONFIG_WLAN_GRACE) += exynos8890-gracelte_eur_open_11.dtb

targets += dtbs
DTB_LIST  := $(dtb-y) $(dtbo-y)

ifeq ($(CONFIG_EXYNOS_DTBTOOL),y)
targets += dtb.img

DTB_OBJS += $(shell find -L $(obj)/dts/ -name \*.dtb)

$(obj)/dtb.img: $(DTB_OBJS) FORCE
	$(call if_changed,dtbtool_exynos)
endif

dtbs: $(addprefix $(obj)/, $(DTB_LIST))

clean-files := *.dtb*
