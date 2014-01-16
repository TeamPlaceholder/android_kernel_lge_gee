CFLAGS_scm.o :=$(call as-instr,.arch_extension sec,-DREQUIRES_SEC=1)

obj-y += io.o dma.o memory.o
ifndef CONFIG_ARM_ARCH_TIMER
obj-y += timer.o
endif
obj-y += clock-voter.o
obj-$(CONFIG_USE_OF) += board-dt.o
obj-$(CONFIG_DEBUG_FS) += nohlt.o

obj-y += acpuclock.o
obj-$(CONFIG_ARCH_MSM_KRAIT) += clock-krait.o
obj-$(CONFIG_MSM_CORTEX_A7) += clock-a7.o
obj-$(CONFIG_HW_PERF_EVENTS) += perf_trace_counters.o
obj-$(CONFIG_ARCH_MSM_KRAIT) += msm-krait-l2-accessors.o perf_event_msm_krait_l2.o
obj-$(CONFIG_ARCH_MSM_KRAIT) += krait-scm.o
obj-$(CONFIG_DEBUG_FS) += perf_debug.o

obj-$(CONFIG_SMP) += headsmp.o platsmp.o
obj-$(CONFIG_HOTPLUG_CPU) += hotplug.o

obj-$(CONFIG_MSM_AVS_HW) += avs.o
obj-$(CONFIG_CPU_V7) += idle-v7.o
obj-$(CONFIG_MSM_JTAG) += jtag-fuse.o jtag.o
obj-$(CONFIG_MSM_JTAG_MM) +=  jtag-fuse.o jtag-mm.o

quiet_cmd_mkrpcsym = MKCAP   $@
      cmd_mkrpcsym = $(PERL) $(srctree)/$(src)/mkrpcsym.pl $< $@

target += smd_rpc_sym.c
$(obj)/smd_rpc_sym.c: $(src)/smd_rpc_sym $(src)/mkrpcsym.pl
	$(call if_changed,mkrpcsym)

obj-$(CONFIG_MSM_SMD) += smd.o smd_debug.o smd_private.o smd_init_dt.o smsm_debug.o
obj-$(CONFIG_MSM_SMP2P) += smp2p.o smp2p_debug.o smp2p_gpio.o
obj-$(CONFIG_MSM_SMP2P_TEST) += smp2p_loopback.o smp2p_test.o smp2p_gpio_test.o smp2p_spinlock_test.o
obj-$(CONFIG_MSM_SCM) += scm.o scm-boot.o
obj-$(CONFIG_MSM_XPU_ERR_FATAL) += scm-xpu.o
obj-$(CONFIG_MSM_PIL) += peripheral-loader.o
obj-$(CONFIG_MSM_PIL_SSR_GENERIC) += subsys-pil-tz.o
obj-$(CONFIG_MSM_PIL) += scm-pas.o
obj-$(CONFIG_MSM_PIL_LPASS_QDSP6V5) += pil-q6v5.o pil-q6v5-lpass.o
obj-$(CONFIG_MSM_PIL_MSS_QDSP6V5) += pil-q6v5.o pil-msa.o pil-q6v5-mss.o
obj-$(CONFIG_MSM_PIL_PRONTO) += pil-pronto.o
obj-$(CONFIG_MSM_PIL_VENUS) += pil-venus.o
obj-$(CONFIG_MSM_PIL_VPU) += pil-vpu.o
obj-$(CONFIG_MSM_PIL_FEMTO) += pil-q6v5.o pil-msa.o pil-femto-modem.o
obj-$(CONFIG_MSM_PIL_BCSS) += pil-bcss.o
obj-$(CONFIG_MSM_BAM_DMUX) += bam_dmux.o
obj-$(CONFIG_MSM_SMD_LOGGING) += smem_log.o
obj-y += socinfo.o
obj-$(CONFIG_MSM_QMI_INTERFACE) += msm_qmi_interface.o
obj-$(CONFIG_MSM_TEST_QMI_CLIENT) += kernel_test_service_v01.o test_qmi_client.o
obj-$(CONFIG_DEBUG_FS) += smd_rpc_sym.o
obj-y += qdsp6v2/
obj-$(CONFIG_PM) += pm-boot.o
obj-$(CONFIG_MSM_IDLE_STATS) += pm-stats.o
obj-$(CONFIG_MSM_NOPM) += no-pm.o

obj-$(CONFIG_MSM_PCIE) += pcie.o pcie_irq.o pcie_phy.o

obj-$(CONFIG_MSM_SPM_V2) += spm-v2.o spm_devices.o

obj-$(CONFIG_MSM_DMA_TEST) += dma_test.o
obj-$(CONFIG_SURF_FFA_GPIO_KEYPAD) += keypad-surf-ffa.o

obj-$(CONFIG_MSM_BOOT_STATS) += boot_stats.o

obj-$(CONFIG_MSM_SPM_REGULATOR) += spm-regulator.o

ifdef CONFIG_MSM_SUBSYSTEM_RESTART
	obj-y += subsystem_notif.o
	obj-y += subsystem_restart.o
	obj-y += ramdump.o
endif
obj-$(CONFIG_MSM_SYSMON_COMM) += sysmon.o

obj-$(CONFIG_CPU_IDLE) += cpuidle.o

obj-$(CONFIG_ARCH_FSM9900) += board-fsm9900.o board-fsm9900-gpiomux.o
obj-$(CONFIG_ARCH_FSM9900) += clock-local2.o clock-pll.o clock-fsm9900.o clock-rpm.o clock-voter.o
obj-$(CONFIG_ARCH_FSM9900) += clock-krait-8974.o
obj-$(CONFIG_ARCH_FSM9900) += rfic-fsm9900.o bbif-fsm9900.o
obj-$(CONFIG_MSM_WATCHDOG_V2) += msm_watchdog_v2.o
obj-$(CONFIG_MSM_MEMORY_DUMP) += msm_memory_dump.o
obj-$(CONFIG_MACH_MSM8X60_SURF) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_FFA) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_FLUID) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_DRAGON) += board-msm8x60.o
obj-$(CONFIG_MACH_TYPE_MSM8X60_FUSION) += board-msm8x60.o mdm.o
obj-$(CONFIG_MACH_MSM8X60_FUSN_FFA) += board-msm8x60.o mdm.o
obj-$(CONFIG_TROUT_H2W) += board-trout-h2w.o
obj-$(CONFIG_TROUT_BATTCHG) += htc_battery.o
obj-$(CONFIG_TROUT_PWRSINK) += htc_pwrsink.o
obj-$(CONFIG_ARCH_MSM7X27) += clock-pcom-lookup.o
obj-$(CONFIG_MACH_MSM7X27_SURF) += board-msm7x27.o devices-msm7x27.o
obj-$(CONFIG_MACH_MSM7X27_FFA) += board-msm7x27.o devices-msm7x27.o
obj-$(CONFIG_ARCH_MSM7X27A) += clock-pcom-lookup.o devices-msm7x27a.o
board-7627a-all-objs += board-msm7627a-storage.o board-msm7627a-bt.o board-msm7627a-camera.o
board-7627a-all-objs += board-msm7627a-display.o board-msm7627a-wlan.o board-msm7627a-io.o
obj-$(CONFIG_MACH_MSM7X27A_RUMI3) += board-msm7x27a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM7X27A_SURF) += board-msm7x27a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM7X27A_FFA) += board-msm7x27a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM7627A_QRD1) += board-qrd7627a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM7627A_QRD3) += board-qrd7627a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM7627A_EVB) += board-qrd7627a.o board-7627a-all.o
obj-$(CONFIG_ARCH_MSM8625) += msm_smem_iface.o devices-msm7x27a.o clock-pcom-lookup.o mpm-8625.o
obj-$(CONFIG_MACH_MSM8625_RUMI3) += board-msm7x27a.o
obj-$(CONFIG_MACH_MSM8625_SURF) +=  board-msm7x27a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM8625_EVB) +=  board-qrd7627a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM8625_QRD7) +=  board-qrd7627a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM8625_FFA) += board-msm7x27a.o board-7627a-all.o
obj-$(CONFIG_MACH_MSM8625_EVT) += board-msm7x27a.o board-7627a-all.o
obj-$(CONFIG_ARCH_MSM7X30) += board-msm7x30.o devices-msm7x30.o memory_topology.o
obj-$(CONFIG_ARCH_MSM7X30) += clock-local.o clock-7x30.o acpuclock-7x30.o clock-pll.o
obj-$(CONFIG_MACH_MSM7X25_SURF) += board-msm7x27.o devices-msm7x25.o
obj-$(CONFIG_MACH_MSM7X25_FFA) += board-msm7x27.o devices-msm7x25.o
obj-$(CONFIG_ARCH_MSM8960) += clock-local.o clock-dss-8960.o clock-8960.o clock-rpm.o clock-pll.o
obj-$(CONFIG_ARCH_MSM8960) += footswitch-8x60.o
obj-$(CONFIG_ARCH_MSM8960) += acpuclock-8960.o acpuclock-8960ab.o
obj-$(CONFIG_ARCH_MSM8960) += memory_topology.o
obj-$(CONFIG_ARCH_MSM8960) += saw-regulator.o
obj-$(CONFIG_ARCH_MSM8960) += devices-8960.o
obj-$(CONFIG_ARCH_APQ8064) += devices-8960.o devices-8064.o
obj-$(CONFIG_ARCH_APQ8064) += acpuclock-8064.o
board-8960-all-objs += board-8960.o board-8960-camera.o board-8960-display.o board-8960-pmic.o board-8960-storage.o board-8960-gpiomux.o
board-8930-all-objs += board-8930.o board-8930-camera.o board-8930-display.o board-8930-pmic.o board-8930-storage.o board-8930-gpiomux.o devices-8930.o board-8930-gpu.o
board-8064-all-objs += board-8064.o board-8064-pmic.o board-8064-storage.o board-8064-gpiomux.o board-8064-camera.o board-8064-display.o board-8064-gpu.o
obj-$(CONFIG_MACH_MSM8960_CDP) += board-8960-all.o board-8960-regulator.o
obj-$(CONFIG_MACH_MSM8960_MTP) += board-8960-all.o board-8960-regulator.o
obj-$(CONFIG_MACH_MSM8960_FLUID) += board-8960-all.o board-8960-regulator.o
obj-$(CONFIG_MACH_MSM8930_CDP) += board-8930-all.o board-8930-regulator.o
obj-$(CONFIG_MACH_MSM8930_MTP) += board-8930-all.o board-8930-regulator.o
obj-$(CONFIG_MACH_MSM8930_FLUID) += board-8930-all.o board-8930-regulator.o
obj-$(CONFIG_PM8921_BMS) += bms-batterydata.o bms-batterydata-desay.o
obj-$(CONFIG_MACH_APQ8064_CDP) += board-8064-all.o board-8064-regulator.o
ifndef CONFIG_MACH_LGE # FIXME: will be fixed
obj-$(CONFIG_MACH_APQ8064_MTP) += board-8064-all.o board-8064-regulator.o
endif
obj-$(CONFIG_MACH_APQ8064_LIQUID) += board-8064-all.o board-8064-regulator.o
obj-$(CONFIG_MACH_MPQ8064_HRD) += board-8064-all.o board-8064-regulator.o
obj-$(CONFIG_MACH_MPQ8064_DTV) += board-8064-all.o board-8064-regulator.o
obj-$(CONFIG_ARCH_MSM9615) += board-9615.o devices-9615.o board-9615-regulator.o board-9615-gpiomux.o board-9615-storage.o board-9615-display.o
obj-$(CONFIG_ARCH_MSM9615) += clock-local.o clock-9615.o acpuclock-9615.o clock-rpm.o clock-pll.o
obj-$(CONFIG_ARCH_MSM8974) += board-8974.o board-dt.o board-8974-gpiomux.o
obj-$(CONFIG_ARCH_MSM8974) += acpuclock-8974.o
obj-$(CONFIG_ARCH_MSM8974) += clock-local2.o clock-pll.o clock-8974.o clock-rpm.o clock-voter.o
obj-$(CONFIG_ARCH_MSM8974) += gdsc.o
obj-$(CONFIG_ARCH_MSM8226) += gdsc.o
obj-$(CONFIG_ARCH_MSM8610) += gdsc.o
obj-$(CONFIG_ARCH_MPQ8092) += gdsc.o
obj-$(CONFIG_ARCH_APQ8084) += gdsc.o
obj-$(CONFIG_ARCH_MSMKRYPTON) += gdsc.o
obj-$(CONFIG_QPNP_BMS) += bms-batterydata.o bms-batterydata-desay.o
obj-$(CONFIG_QPNP_BMS) += bms-batterydata-oem.o bms-batterydata-qrd-4v35-2000mah.o bms-batterydata-qrd-4v2-1300mah.o
obj-$(CONFIG_ARCH_APQ8084) += board-8084.o board-8084-gpiomux.o
obj-$(CONFIG_ARCH_APQ8084) += clock-local2.o clock-pll.o clock-8084.o clock-rpm.o clock-voter.o clock-mdss-8974.o
obj-$(CONFIG_ARCH_APQ8084) += clock-krait-8974.o
obj-$(CONFIG_ARCH_MSM8974) += board-8974.o board-8974-gpiomux.o
obj-$(CONFIG_ARCH_MSM8974) += clock-krait-8974.o
obj-$(CONFIG_ARCH_MSM8974) += clock-local2.o clock-pll.o clock-rpm-8974.o clock-gcc-8974.o clock-mmss-8974.o clock-lpass-8974.o clock-rpm.o clock-voter.o clock-mdss-8974.o
obj-$(CONFIG_KRAIT_REGULATOR) += krait-regulator.o  krait-regulator-pmic.o
obj-$(CONFIG_ARCH_MDM9630) += board-9630.o board-9630-gpiomux.o
obj-$(CONFIG_ARCH_MSMSAMARIUM) += board-samarium.o board-samarium-gpiomux.o
obj-$(CONFIG_ARCH_MSMSAMARIUM) += clock-local2.o clock-pll.o clock-rpm.o clock-samarium.o clock-krait-8974.o clock-mdss-8974.o
obj-$(CONFIG_ARCH_MPQ8092) += board-8092.o board-8092-gpiomux.o
obj-$(CONFIG_ARCH_MPQ8092) += clock-local2.o clock-pll.o clock-rpm.o clock-voter.o clock-8092.o
obj-$(CONFIG_ARCH_MSM8226) += board-8226.o board-8226-gpiomux.o
obj-$(CONFIG_ARCH_MSM8226) += clock-local2.o clock-pll.o clock-8226.o clock-rpm.o clock-voter.o clock-mdss-8974.o
obj-$(CONFIG_ARCH_MSM8610) += board-8610.o board-8610-gpiomux.o
obj-$(CONFIG_ARCH_MSM8610) += clock-local2.o clock-pll.o clock-8610.o clock-rpm.o clock-voter.o
obj-$(CONFIG_ARCH_MSM8610) += clock-dsi-8610.o
obj-$(CONFIG_ARCH_MDM9630) += clock-local2.o clock-pll.o clock-9630.o clock-rpm.o clock-voter.o
obj-$(CONFIG_ARCH_MDM9630) += clock-alpha-pll.o

obj-$(CONFIG_MSM_PM8X60) += pm-8x60.o pm-data.o

obj-$(CONFIG_MACH_LGE) += board-8960-all.o board-8960-regulator.o
obj-$(CONFIG_MACH_LGE) += lge/

CFLAGS_msm_vibrator.o += -Idrivers/staging/android

obj-$(CONFIG_MSM_RMT_STORAGE_CLIENT) += rmt_storage_client.o
obj-$(CONFIG_MSM_LPM_TEST) += test-lpm.o
obj-$(CONFIG_MSM_RPM_SMD) += rpm-smd.o lpm_levels.o
ifdef CONFIG_DEBUG_FS
obj-$(CONFIG_MSM_RPM_SMD) += rpm-smd-debug.o
endif
obj-$(CONFIG_MSM_MPM_OF) += mpm-of.o
obj-$(CONFIG_MSM_RPM_STATS_LOG) += rpm_stats.o rpm_master_stat.o
obj-$(CONFIG_MSM_RPM_RBCPR_STATS_V2_LOG) += rpm_rbcpr_stats_v2.o
obj-$(CONFIG_MSM_RPM_LOG) += rpm_log.o
obj-$(CONFIG_MSM_TZ_LOG) += tz_log.o
obj-$(CONFIG_MSM_BUS_SCALING) += msm_bus/
obj-$(CONFIG_MSM_BUSPM_DEV) += msm-buspm-dev.o

obj-$(CONFIG_MSM_EVENT_TIMER)		+= event_timer.o

obj-$(CONFIG_MSM_OCMEM) += ocmem.o ocmem_allocator.o ocmem_notifier.o
obj-$(CONFIG_MSM_OCMEM) += ocmem_sched.o ocmem_api.o ocmem_rdm.o ocmem_core.o
obj-$(CONFIG_SENSORS_ADSP) += sensors_adsp.o

obj-$(CONFIG_ARCH_MSM8974) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_MDM9630) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_MSMSAMARIUM) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_MPQ8092) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_MSM8226) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_MSM8610) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_APQ8084) += gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_FSM9900) += gpiomux-v2.o gpiomux.o

obj-$(CONFIG_MSM_RUN_QUEUE_STATS) += msm_rq_stats.o
obj-$(CONFIG_MSM_SHOW_RESUME_IRQ) += msm_show_resume_irq.o
obj-$(CONFIG_MSM_NATIVE_RESTART) += restart.o

obj-$(CONFIG_MSM_CACHE_ERP) += cache_erp.o
obj-$(CONFIG_MSM_CACHE_DUMP) += msm_cache_dump.o

obj-$(CONFIG_MSM_HSIC_SYSMON) += hsic_sysmon.o
obj-$(CONFIG_MSM_HSIC_SYSMON_TEST) += hsic_sysmon_test.o

obj-$(CONFIG_MSM_RPM_SMD) += rpm-smd.o
obj-$(CONFIG_MSM_RPC_USB) += rpc_hsusb.o rpc_fsusb.o

obj-$(CONFIG_MSM_ENABLE_WDOG_DEBUG_CONTROL) += wdog_debug.o

obj-$(CONFIG_MEMORY_HOLE_CARVEOUT) +=  msm_mem_hole.o

obj-$(CONFIG_MSM_SMCMOD) += smcmod.o

obj-$(CONFIG_ARCH_MSM8974) += msm_mpmctr.o
obj-$(CONFIG_MSM_CPR_REGULATOR) += cpr-regulator.o
obj-$(CONFIG_CPU_FREQ_MSM) += cpufreq.o
obj-$(CONFIG_MSM_DEVFREQ_CPUBW) += devfreq_cpubw.o


obj-$(CONFIG_ARCH_RANDOM) += early_random.o
obj-$(CONFIG_PERFMAP) += perfmap.o
