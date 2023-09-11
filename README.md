使用的固件是hzyitc/openwrt-redmi-ax3000

固件默认是使用wpad-basic-wolfssl，导致开启802.11v后无线不能正常工作

把wpad-basic-wolfssl替换成wpad-openssl
然后在/etc/config/wireless设定以下：
option ieee80211k '1'
option ieee80211r '1'
option bss_transition "1"
option wnm_sleep_mode "1"
option time_advertisement "2"
option time_zone "GMT0"
option ft_over_ds '0'
option ft_psk_generate_local '1'
option encryption 'psk2+ccmp'

已成功开启802.11krv