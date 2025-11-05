```
已安装文件：
- /etc/systemd/system/xray.service
- /etc/systemd/system/xray@.service

- /home/xray/xray
- /home/xray/*.json

- /home/xray/dat/geoip.dat
- /home/xray/dat/geosite.dat

- /home/xray/log/access.log
- /home/xray/log/error.log
```

注意：Xray 默认不会将日志记录到 `/home/xray/log/*.log`。请配置 `"log"` 来指定日志文件。

## 基本用法

**安装并升级 Xray-core 和地理数据，默认使用 `User=nobody`，但不会覆盖已有服务文件中的 `User` 设置**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install
```

**仅更新 geoip.dat 和 geosite.dat**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install-geodata
```

**移除 Xray，但保留 json 配置文件和日志**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ remove
```

## 高级用法

**安装并升级 Xray-core 到预发布版本**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install --beta
```

**安装并升级 Xray-core 和地理数据，并启用 `logrotate`，`$time` 可以是 12:34:56 格式的时间**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install --logrotate $time
```

```
已安装文件：
- /etc/systemd/system/logrotate@.service
- /etc/systemd/system/logrotate@.timer
- /etc/logrotate.d/xray
```

**安装并升级 Xray-core 和地理数据，使用 `User=root`，会覆盖已有服务文件中的 `User` 设置**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install -u root
```

**安装并升级 Xray-core，但不包含地理数据**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install --without-geodata
```

**移除 Xray，包括 json 配置文件和日志**

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ remove --purge
```

## 更多用法

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ help
```
