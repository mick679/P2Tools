# PKSTool-Suite

PKS工具包 - Honeywell Experion PKS 工具集合

## 简介

PKSTool-Suite 是一套针对 Honeywell Experion PKS 系统的实用工具集合，提供多种功能帮助工程师提高工作效率。

## 功能模块

### 1. CNF Analyzer (CNF 分析器)
- **版本**: 1.1
- **用途**: 批量分析 CNF XML 文件，提取模块、控制器、连接与参数引用，识别跨模块及跨控制器引用关系
- **主要功能**:
  - 支持批量加载和分析 *.cnf.xml 文件
  - 自动检测和修复 XML 编码问题
  - 提取模块信息和控制器映射
  - 分析跨控制器引用关系
  - 导出分析结果为 Excel 或 CSV 格式

### 2. Excel 批量建点
- **版本**: 1.1
- **用途**: 根据标签文件第一列批量展开模板数据区域并替换指定列值
- **主要功能**:
  - 批量复制和替换 Excel 模板数据
  - 自动调整公式中的行号引用
  - 保留单元格样式和格式
  - 支持多标签批量处理

### 3. Excel 比较工具
- **版本**: 1.1
- **用途**: 比较 2-3 个 Excel Sheet 的差异
- **主要功能**:
  - 逐格比较 Excel 单元格
  - 高亮显示差异单元格
  - 导出差异报告（CSV 或高亮 Excel）
  - 支持多文件同时比较

### 4. 分程曲线求解器
- **版本**: 1.1
- **用途**: 根据两个点计算直线方程 y = kx + b
- **主要功能**:
  - 快速计算斜率和截距
  - 显示完整的线性方程
  - 输入验证和错误提示

### 5. AlarmGroup 清理工具
- **版本**: 1.1
- **用途**: 删除 XML 文件中匹配关键字的 Parameter 并重新编号
- **主要功能**:
  - 支持关键字匹配删除
  - 自动重新编号 ITEMS[...]
  - 更新 ITEMCNT 计数
  - 测试模式预览匹配项

### 6. Station 自动截屏工具
- **版本**: 1.1
- **用途**: 批量向 Station 命令输入框输入文件名并自动截图
- **主要功能**:
  - 自动附着 Station 窗口
  - 批量输入命令和截图
  - 自动保存 PNG 格式截图
  - 支持自定义等待时间

### 7. IO清单整理工具
- **版本**: 7.0
- **用途**: Excel 数据映射提取工具，根据示例模板自动或手动映射源 Excel 数据
- **主要功能**:
  - 生成和加载示例输入/输出模板
  - 自动或手动设置数据映射关系
  - 支持条件表达式和多规则优先级执行
  - 验证并修正表头
  - 数据提取导出（Process 和 Result 表）
  - 结果列拆分（值/单位分离）
  - 配置保存和加载
  - 适合批量 IO 清单整理和数据规范化处理

## 安装要求

### Python 版本
- Python 3.6 或更高版本

### 依赖库

```bash
pip install -r requirements.txt
```

主要依赖：
- pandas - 数据处理
- openpyxl - Excel 文件操作
- pyinstaller - 打包工具
- numpy - 数值计算
- pywin32 - Windows API 支持
- mss - 屏幕截图
- psutil - 进程管理
- pywinauto - UI 自动化（可选）

## 使用方法

### 启动主应用程序

```bash
python combined_app.py
```

### 独立运行工具

每个工具都可以独立运行：

```bash
# CNF 分析器
python cnf_analyzer_gui.py

# Excel 批量建点
python excel_processor_main.py

# Excel 比较
python excel_compare.py

# 分程曲线求解器
python linear_equation_solver.py

# AlarmGroup 清理
python XMLParamValueRemover.py

# Station 截屏
python station_auto_capture_V14.py

# IO清单整理工具
python excel_mapper_gui_Version7.py
```

### 命令行参数

主应用程序支持 `--tool` 参数直接启动特定工具：

```bash
python combined_app.py --tool=excel_compare
python combined_app.py --tool=excel_processor
python combined_app.py --tool=linear
python combined_app.py --tool=alarm
```

## 注意事项

1. **文件备份**: 处理 XML 或 Excel 文件前，请务必备份原始文件
2. **编码问题**: CNF Analyzer 会自动尝试多种编码（UTF-16, UTF-8, GBK），但某些特殊编码可能需要手动转换
3. **依赖检查**: Station 截屏工具依赖 pywin32、mss 和 psutil，缺失会影响功能
   - 如果使用 PyInstaller 打包后遇到依赖问题，请参考 [PACKAGING_WINDOWS_DEPENDENCIES.md](PACKAGING_WINDOWS_DEPENDENCIES.md)
4. **Windows 平台**: 部分工具（如 Station 截屏）仅支持 Windows 平台

## 开发者信息

- **作者**: 少帅 (Xueliang Zhang)
- **联系方式**: xueliang.zhang@honeywell.com
- **版权**: 少帅出品，必属精品

## 更新日志

查看 [CHANGELOG.md](CHANGELOG.md) 文件获取详细的版本更新记录。

## 发布和安装

### 从 PyPI 安装

```bash
pip install PKSTool-Suite
```

### 发布新版本

如果您是维护者，查看 [PUBLISHING.md](PUBLISHING.md) 了解如何：
- 发布包到 PyPI
- 创建 GitHub Release
- 版本管理最佳实践

快速参考: [PUBLISHING_QUICKREF.md](PUBLISHING_QUICKREF.md)

## 许可证

本项目使用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。

使用本工具集时，请遵守公司政策和相关软件许可协议。

## 贡献

欢迎贡献！请查看 [CONTRIBUTING.md](CONTRIBUTING.md) 了解如何参与项目。

如有任何问题或建议，请：
- 创建 [GitHub Issue](https://github.com/mick679/PKSTool-Suite/issues)
- 联系作者：xueliang.zhang@honeywell.com
