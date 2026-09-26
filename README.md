# OpenClash APK Repository

基于 GitHub Actions 的 OpenClash APK 自建仓库。
自动获取 [OpenClash](https://github.com/vernesong/OpenClash) 最新 Release 的 APK，重新签名并生成 APK v3 仓库索引 `packages.adb`。

我的使用环境
DISTRIB_TARGET=armsr/armv8
DISTRIB_ARCH=aarch64_generic
apk-tools=3.0.5


## OpenWrt 使用

### 1. 安装公钥

在 OpenWrt 执行：

```sh
wget -O /etc/apk/keys/openclash-apk.pub \
"https://raw.githubusercontent.com/NonArrendertiMai/openclash-apk-repo/main/keys/openclash-apk.pub"
```

### 2. 添加仓库

```sh
cat > /etc/apk/repositories.d/openclash.list <<'EOF'
https://raw.githubusercontent.com/NonArrendertiMai/openclash-apk-repo/main/repo/packages.adb
EOF
```

### 3. 安装 OpenClash

```sh
apk add luci-app-openclash
```
