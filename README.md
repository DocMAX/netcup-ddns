# netcup-ddns
This is a simple script to update DNS-records hosted by [netcup](https://netcup.de). It is implemented in [lua](https://lua.org), so that it can be run on [OpenWRT](https://openwrt.org) routers. The script needs to be edited to contain the customer specific information. All subdomains (except "mail") will be changed to point to the public ip of the device this script is being run on.

## Files

### ddns.lua
Original version using external IP lookup services (v4.ident.me and v6.ident.me) to determine public IP addresses.

### ddns-openwrt.lua
Optimized version for OpenWRT that uses local ubus API to retrieve WAN IP addresses directly from the router's network interfaces, eliminating the need for external IP lookup services. This version is faster and more reliable for OpenWRT devices.

## Dependencies
- luasocket
- luasec
- luci-lib-jsonc (a lightweight alternative to lua-cjson)
