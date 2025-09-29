# 农历日历 (Chinese Calendar)

一款传统的农历日历应用，最初为 Ubuntu Kylin 开发。它能同时显示公历和农历，并包含中国的传统节日和二十四节气。

这个版本库已经更新，可以在现代的、基于 Debian 的 Linux 发行版（如 Ubuntu 22.04+、Linux Mint 22+）上成功构建和运行。
## 下载运行
可以直接下载deb包安装运行，在linux mint 22+ 上测试通过。

![截图 1](https://www.ubuntukylin.com/public/images/928_nl1.png)
![截图 2](https://www.ubuntukylin.com/public/images/928_nl2.png)

## 功能特性

- 同时显示公历与农历。
- 高亮显示中国的传统节日和二十四节气。
- 支持方便地按年月进行查询。
- 专为中文用户习惯设计的界面。

## 在 Debian/Ubuntu/Linux Mint 上从源码构建

本项目被配置为构建成一个原生的 Debian 软件包 (`.deb`)，这是推荐的安装方式。

### 1. 克隆仓库

首先，克隆本仓库并进入项目目录。本项目使用了一个 Git 子模块，因此你必须使用递归克隆来确保子模块被一同下载。

```bash
git clone --recursive https://github.com/YOUR_USERNAME/chinese-calendar.git
cd chinese-calendar
```

*如果你已经克隆了仓库但忘记了初始化子模块，可以运行以下命令来补救：*
```bash
git submodule update --init --recursive
```

### 2. 安装构建依赖

安装编译和打包所需的工具及 Qt5 开发库。

```bash
sudo apt-get update
sudo apt-get install -y build-essential devscripts debhelper qtbase5-dev libqt5svg5-dev qt5-qmake
```

### 3. 构建 Debian 软件包

在项目根目录运行以下命令来构建 `.deb` 软件包。

```bash
dpkg-buildpackage -us -uc -b
```

### 4. 安装软件包

构建过程结束后，你会在上级目录找到生成的 `.deb` 文件。你可以使用 `apt` 来安装它。

```bash
sudo apt install ../chinese-calendar_*.deb
```

安装完成后，你就可以在应用程序菜单中找到“优客日历”了。

## 许可证

本项目使用 GPL-3.0 许可证。详情请参阅 `COPYING` 文件。
