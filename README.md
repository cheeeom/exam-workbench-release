# 教师试卷工作台 · 更新清单

这个仓库**只放一个文件**：`latest.json`。它是桌面版「检查更新」唯一读取的东西。

- 没有代码
- 没有安装包
- 没有你的任何数据

安装包本身不公开：看到提示后请联系作者领取。装好即用，数据全部留在你自己的电脑上。

## 客户端读哪个地址

主源（GitHub Pages）：

```
https://cheeeom.github.io/exam-workbench-release/latest.json
```

备源（jsDelivr，主源不通时自动换）：

```
https://cdn.jsdelivr.net/gh/cheeeom/exam-workbench-release@main/latest.json
```

两次请求都是普通 HTTPS GET，不带任何标识、不上传任何东西、失败就静默——断网时应用照常组卷。

## latest.json 各字段

| 字段 | 说明 |
| --- | --- |
| `schemaVersion` | 固定 `1`，将来格式变才动 |
| `version` | 最新版本号，三段数字，如 `2.8.0` |
| `releasedAt` | 发布日期，`YYYY-MM-DD` |
| `pageUrl` | 「去下载」按钮打开的地址，必须 `https://`。指向在哪拿安装包 |
| `critical` | `true` 时客户端不给「忽略此版本」，只提示更新 |
| `notes` | 更新说明，字符串数组，最多 12 条，每条 400 字内 |

版本比较是逐段数字比，`2.10.0` 大于 `2.9.0`。清单写错（字段缺失、版本号不是数字、地址不是 https）客户端会当成「没有清单」，静默跳过，不会崩。
