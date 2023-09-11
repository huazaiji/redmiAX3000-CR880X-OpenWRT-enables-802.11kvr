The firmware used is github:hzyitc/openwrt-redmi-ax3000

The default plug-in for firmware is wpad-basic-wolfssl，As a result, the wireless does not work properly after 802.11v is turned on

Replace wpad-basic-wolfssl with wpad-openssl

Then set /etc/config/wireless to the following:

option ieee80211k '1'

option ieee80211r '1'

option bss_transition "1"

option wnm_sleep_mode "1"

option time_advertisement "2"

option time_zone "GMT0"

option ft_over_ds '0'

option ft_psk_generate_local '1'

option encryption 'psk2+ccmp'



802.11krv has been successfully enabled！
