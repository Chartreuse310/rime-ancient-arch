# 中国古建筑词库 (Rime Ancient Architecture Dictionary)

这是一个为 [Rime 输入法](https://github.com/rime/squirrel) 和 [雾凇拼音 (Rime-ice)](https://github.com/iDvel/rime-ice) 配置的中国古建筑术语词库。旨在解决研究《营造法式》《工程做法》等文献时查找词汇困难的问题。

## 安装与配置

配置此词库前，请确保您已安装 Rime 输入法及雾凇拼音词库。

### 配置步骤

1. **安装 Rime 输入法**
   根据您的操作系统安装对应的 Rime 发行版（如 macOS 上的 [Squirrel](https://github.com/rime/squirrel)）。
2. **安装雾凇拼音**
   按照 [雾凇拼音 (Rime-ice)](https://github.com/iDvel/rime-ice) 的官方说明完成安装。
3. **放置词典文件**
   将本仓库中的 [ancient\_arch.dict.yaml](file:///Users/z/Programs/rime-ancient-arch/ancient_arch.dict.yaml) 文件放置到 Rime 用户配置目录下的 `cn_dicts` 文件夹中。
4. **在雾凇拼音配置中引入词典**
   在您的 `rime_ice.dict.yaml` 中，将 `ancient_arch` 添加到 `import_tables` 下。
5. **添加自定义配置补丁**
   将本仓库中的 [rime\_ice.custom.yaml](file:///Users/z/Programs/rime-ancient-arch/rime_ice.custom.yaml) 加入 Rime 配置文件夹。

配置好后，`rime.arch.dict.yaml` 应该看起来像这样：

```YAML
---
name: rime_ice
version: "2026-01-26"
import_tables:
  - cn_dicts/8105     # 字表
  # - cn_dicts/41448  # 大字表（按需启用）（启用时和 8105 同时启用并放在 8105 下面）
  - cn_dicts/base     # 基础词库
  - cn_dicts/ext      # 扩展词库
  - cn_dicts/tencent  # 腾讯词向量（大词库，部署时间较长）
  - cn_dicts/others   # 一些杂项
  - cn_dicts/ancient_arch  # 古建筑词库

  # 建议把扩展词库放到下面，有重复词条时，最上面的权重生效
  # - mydict1           # 挂载配置目录下的 mydict1.dict.yaml 词库文件
  # - cn_dicts/mydict2  # 挂载 cn_dicts 目录里的 mydict2.dict.yaml 词库文件
...
```

## 文件说明

- `ancient_arch.dict.yaml`: 核心词库文件，包含中国古建筑相关术语。
- `rime_ice.custom.yaml`: 用于雾凇拼音的自定义配置补丁，确保词库能够被正确加载和调用。

## 重新部署

完成上述步骤后，请在 Rime 输入法菜单中选择 **“重新部署” (Deploy)**，即可开始使用。

## 致谢

- 感谢 [Rime](https://github.com/rime/squirrel) 提供的强大输入引擎。
- 感谢 [雾凇拼音 (Rime-ice)](https://github.com/iDvel/rime-ice) 提供的优秀基础词库。
