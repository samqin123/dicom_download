# dicom_download

这是给患者和家属用的文本菜单版入口。

## 怎么启动

直接运行：

```bash
uv run python main.py
```

启动后会看到一个菜单：

1. 单 URL 下载（粘贴一个链接）
2. 本地 txt 批量下载（输入 txt 路径）
3. 默认读取当前目录 `urls.txt`（直接回车即可）
4. 查看配置
5. 修改并保存配置
6. 保存当前配置
7. 退出

## 第一次使用

先准备这三样：

1. 安装 Python 3.10+
2. 安装 uv
3. 安装 Playwright 浏览器：

```bash
uv sync
uv run python -m playwright install chromium
```

## 最常用的操作

### 单个链接

在菜单里选 **1**，然后粘贴链接。

### 一次多个链接

在菜单里选 **2**，输入本地 txt 文件路径。txt 里每行一个链接。

### 直接用当前目录的 urls.txt

在菜单里选 **3**。如果当前目录里有 `urls.txt`，就会直接读取。

## 配置怎么改

菜单里选 **4** 可以查看当前配置。

菜单里选 **5** 可以修改后保存：

- provider
- mode
- 是否无界面
- `max_rounds`
- `step_wait_ms`
- 输出目录
- 是否跳过高清切换
- 是否生成 zip
- 是否覆盖旧目录

如果出现下面这句：

```text
>>> ⚠ 可能未完整命中全部切片，可尝试提高 max_rounds 或增大 step_wait_ms
```

就把这两个值调大一些。

## 自动生成配置

第一次运行时，如果当前目录没有 `dicom_download.toml`，程序会自动生成一个默认模板。

你也可以用菜单里的 **6** 保存当前配置。

## 常见问题

### 提示浏览器不存在

重新执行：

```bash
uv run python -m playwright install chromium
```

### 提示 Python 包缺失

重新执行：

```bash
uv sync
```

## 致谢与合规

- 感谢引用上游项目的开源实现与思路
- 感谢小胰宝志愿者开源贡献
- **禁止使用本工具向患者收费或变相收费**

## 站点说明

- zlyy.tjmucih.cn：天肿
- ylyyx.shdc.org.cn：复肿
- zhyl.nyfy.com.cn：宁夏总医院

## 高级用法

如果你是熟练用户，也可以继续直接看 `main.py --help`。
