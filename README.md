# openwrt_config
OpenWrt OpenvSwitch Config file

config interface 'loopback'
        option ifname 'lo'
        option proto 'static'
        option ipaddr '127.0.0.1'
        option netmask '255.0.0.0'

config globals 'globals'
        option ula_prefix 'fd2d:6d3b:a179::/48'

config interface 'lan'
        option ifname 'eth0.1'
        option force_link '1'
        option type 'bridge'
        option proto 'static'
        option netmask '255.255.255.0'
        option ip6assign '60'
        option ipaddr '10.0.0.1'

config interface 'wan'
        option ifname 'eth0.2'
        option force_link '1'
        option proto 'dhcp'

config interface 'wan6'
        option ifname 'eth0.2'
        option proto 'dhcpv6'

config switch
        option name 'switch0'
        option reset '1'
        option enable_vlan '1'

config switch_vlan
        option device 'switch0'
        option vlan '1'
        option ports '1 2 3 4 5t'

config switch_vlan
        option device 'switch0'
        option vlan '2'
        option ports '0 5t'
