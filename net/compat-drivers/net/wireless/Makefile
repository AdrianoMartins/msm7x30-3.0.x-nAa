obj-$(CONFIG_CFG80211) += cfg80211.o

cfg80211-y += core.o sysfs.o radiotap.o util.o reg.o scan.o nl80211.o
cfg80211-y += mlme.o ibss.o sme.o chan.o ethtool.o mesh.o ap.o
cfg80211-$(CONFIG_COMPAT_CFG80211_DRIVER_API_TRACER) += trace.o
cfg80211-$(CONFIG_CFG80211_DEBUGFS) += debugfs.o
cfg80211-$(CONFIG_CFG80211_WEXT) += wext-compat.o wext-sme.o
cfg80211-$(CONFIG_CFG80211_INTERNAL_REGDB) += regdb.o

CFLAGS_trace.o := -I$(src)

ccflags-y += -D__CHECK_ENDIAN__

$(obj)/regdb.c: $(src)/db.txt $(src)/genregdb.awk
	@$(AWK) -f $(src)/genregdb.awk < $< > $@

clean-files := regdb.c
