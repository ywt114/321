# 删除替换默认源插件
rm -rf feeds/packages/lang/golang
svn export https://github.com/sbwml/packages_lang_golang/branches/19.x feeds/packages/lang/golang
rm -rf feeds/packages/net/smartdns
svn export https://github.com/pymumu/openwrt-smartdns/trunk feeds/packages/net/smartdns
rm -rf feeds/packages/net/adguardhome
svn export https://github.com/kenzok8/openwrt-packages/trunk/adguardhome feeds/packages/net/adguardhome
rm -rf feeds/packages/net/socat
svn export https://github.com/xiangfeidexiaohuo/openwrt-packages/trunk/op-socat/socat feeds/packages/net/socat
rm -rf feeds/packages/net/mosdns
svn export https://github.com/kenzok8/openwrt-packages/trunk/mosdns feeds/packages/net/mosdns
rm -rf feeds/packages/utils/v2dat
svn export https://github.com/kenzok8/openwrt-packages/trunk/v2dat feeds/packages/utils/v2dat

# 添加插件
cd package/lean
svn export https://github.com/ywt114/luci-app-advanced/trunk ./luci-app-advanced
svn export https://github.com/pymumu/luci-app-smartdns/branches/lede ./luci-app-smartdns
svn export https://github.com/sirpdboy/chatgpt-web/trunk ./luci-app-chatgpt
svn export https://github.com/fw876/helloworld/trunk/luci-app-ssr-plus ./luci-app-ssr-plus
svn export https://github.com/xiaorouji/openwrt-passwall/branches/luci/luci-app-passwall ./luci-app-passwall
svn export https://github.com/vernesong/OpenClash/trunk/luci-app-openclash ./luci-app-openclash
svn export https://github.com/kenzok8/openwrt-packages/trunk/luci-app-adguardhome ./luci-app-adguardhome
svn export https://github.com/kenzok8/openwrt-packages/trunk/luci-app-mosdns ./luci-app-mosdns
svn export https://github.com/xiangfeidexiaohuo/openwrt-packages/trunk/op-socat/luci-app-socat ./luci-app-socat
svn export https://github.com/xiangfeidexiaohuo/openwrt-packages/trunk/op-homebox ./op-homebox
svn export https://github.com/sbwml/luci-app-alist/trunk ./op-alist
svn export https://github.com/sirpdboy/luci-app-autotimeset/trunk ./luci-app-autotimeset
sed -i 's/control"/system"/g' luci-app-autotimeset/luasrc/controller/autotimeset.lua
svn export https://github.com/linkease/istore/trunk ./istore
sed -i 's/+luci-lib-ipkg/+luci-base/g' istore/luci/luci-app-store/Makefile
svn export https://github.com/kenzok8/small/trunk ./small
rm -rf small/luci-app-bypass small/luci-app-passwall small/luci-app-passwall2 small/luci-app-ssr-plus small/luci-app-vssr
