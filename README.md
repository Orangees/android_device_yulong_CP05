# TWRP Device Tree — CoolPad COOL20PRO (Yulong CP05)

TWRP recovery device tree for CoolPad COOL20PRO.

| | |
|---|---|
| **品牌** | Yulong / CoolPad |
| **型号** | COOL20PRO (CP05) |
| **SoC** | MediaTek Dimensity 900 (MT6877) |
| **分区方案** | Virtual A/B |
| **启动方式** | Boot as Recovery |

## 构建

```bash
# 在 TWRP 源码树中
mkdir -p device/yulong/CP05
# 将本仓库内容复制到该目录
cd bootable/recovery
mka recoveryimage
```

## 目录结构

```
├── Android.mk              模块定义
├── AndroidProducts.mk      产品列表
├── BoardConfig.mk          板级配置（分区、内核、TWRP 选项）
├── device.mk               设备模块与属性
├── omni_CP05.mk            产品 makefile
├── recovery.fstab          分区挂载表
├── prebuilt/
│   ├── dtb.img             预编译设备树
│   └── kernel              预编译内核
└── recovery/root/
    └── init.recovery.mt6877.rc   Recovery init 脚本
```

## 已知问题

- system 分区挂载异常
- MTP 无法正常连接
- fastbootd 无法进入

## 参考

- [action_build_twrp_device_tree](https://github.com/momo54181/action_build_twrp_device_tree)
- [recovery_device_xiaomi_pissarro](https://github.com/pjgowtham/recovery_device_xiaomi_pissarro) — 同为 MT6877 的参考树
- AOSP 官方文档

---

**作者：QDY**
