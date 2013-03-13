ifeq ($(CONFIG_FB_MSM_MDSS_COMMON),y)
obj-y += mdss/
else
obj-y := msm_fb.o


ifeq ($(CONFIG_FB_MSM_MDP_HW),y)
# MDP
obj-y += mdp.o


ifeq ($(CONFIG_FB_MSM_MDP40),y)
else
obj-y += mdp_ppp.o
ifeq ($(CONFIG_FB_MSM_MDP31),y)
endif
endif
ifeq ($(CONFIG_FB_MSM_OVERLAY),y)
ifeq ($(CONFIG_FB_MSM_MIPI_DSI),y)
endif
else
endif



# EBI2

# LCDC

# LVDS

# MDDI
msm_mddi-objs := mddi.o
obj-$(CONFIG_FB_MSM_MDDI) += msm_mddi.o

# External MDDI
obj-$(CONFIG_FB_MSM_EXTMDDI) += msm_mddi_ext.o

# MIPI gereric
obj-$(CONFIG_FB_MSM_MIPI_DSI) += msm_mipi.o

# MIPI manufacture
obj-$(CONFIG_FB_MSM_MIPI_DSI_LGIT) += mipi_lgit.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_TOSHIBA) += mipi_toshiba.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_NOVATEK) += mipi_novatek.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_ORISE) += mipi_orise.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_RENESAS) += mipi_renesas.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_TRULY) += mipi_truly.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_NT35510) += mipi_NT35510.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_NT35516) += mipi_truly_tft540960_1_e.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_SIMULATOR) += mipi_simulator.o

# MIPI Bridge

# TVEnc

# MSM FB Panel

ifeq ($(CONFIG_FB_MSM_MIPI_PANEL_DETECT),y)
obj-y += mipi_toshiba_video_wvga_pt.o mipi_toshiba_video_wsvga_pt.o mipi_toshiba_video_wuxga.o
obj-y += mipi_novatek_video_qhd_pt.o mipi_novatek_cmd_qhd_pt.o
obj-y += mipi_orise_video_720p_pt.o mipi_orise_cmd_720p_pt.o
obj-y += mipi_renesas_video_fwvga_pt.o mipi_renesas_cmd_fwvga_pt.o
obj-y += mipi_NT35510_video_wvga_pt.o mipi_NT35510_cmd_wvga_pt.o
obj-y += mipi_truly_tft540960_1_e_video_qhd_pt.o mipi_truly_tft540960_1_e_cmd_qhd_pt.o
obj-y += mipi_chimei_wxga_pt.o
obj-y += mipi_chimei_wuxga.o
obj-y += mipi_truly_video_wvga_pt.o
else
obj-$(CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT) += mipi_lgit_video_wxga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TOSHIBA_VIDEO_WVGA_PT) += mipi_toshiba_video_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TOSHIBA_VIDEO_WSVGA_PT) += mipi_toshiba_video_wsvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TOSHIBA_VIDEO_WUXGA) += mipi_toshiba_video_wuxga.o
obj-$(CONFIG_FB_MSM_MIPI_NOVATEK_VIDEO_QHD_PT) += mipi_novatek_video_qhd_pt.o
obj-$(CONFIG_FB_MSM_MIPI_ORISE_VIDEO_720P_PT) += mipi_orise_video_720p_pt.o
obj-$(CONFIG_FB_MSM_MIPI_ORISE_CMD_720P_PT) += mipi_orise_cmd_720p_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NOVATEK_CMD_QHD_PT) += mipi_novatek_cmd_qhd_pt.o
obj-$(CONFIG_FB_MSM_MIPI_RENESAS_VIDEO_FWVGA_PT) += mipi_renesas_video_fwvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_RENESAS_CMD_FWVGA_PT) += mipi_renesas_cmd_fwvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_RENESAS_VIDEO_FWVGA_PT) += mipi_renesas_video_fwvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TRULY_VIDEO_WVGA_PT) += mipi_truly_video_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NT35510_CMD_WVGA_PT) += mipi_NT35510_cmd_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NT35510_VIDEO_WVGA_PT) += mipi_NT35510_video_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NT35516_CMD_QHD_PT) += mipi_truly_tft540960_1_e_cmd_qhd_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NT35516_VIDEO_QHD_PT) += mipi_truly_tft540960_1_e_video_qhd_pt.o
obj-$(CONFIG_FB_MSM_MIPI_SIMULATOR_VIDEO) += mipi_simulator_video.o
obj-$(CONFIG_FB_MSM_MIPI_CHIMEI_WXGA) += mipi_chimei_wxga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CHIMEI_WUXGA) += mipi_chimei_wuxga.o
endif


ccflags-y := -I$(src)/mhl
obj-$(CONFIG_FB_MSM_HDMI_MHL_8334) += mhl-8334.o


else
endif
endif

obj-$(CONFIG_MSM_VIDC_1080P) += vidc/
obj-$(CONFIG_MSM_VIDC_720P) += vidc/
clean:
	rm *.o .*cmd
