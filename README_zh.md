# 安装 WRF 的脚本

这是一个自动安装 WRF 的脚本，无需 Root 权限。

该脚本由 [Umur Dinç](https://github.com/bakamotokatas/WRF-Install-Script) 的脚本修改而来。

## 前提

在运行脚本安装前，请确保以下包已安装在系统中：

- csh
- wget
- 构建所需的核心工具

## 安装

请将 “wrf_install” 放置在你想安装 WRF 和 WPS 的目录中。

若安装默认模型 **WRF-ARW**, 执行命令:

```bash
bash wrf_install
```

或

```bash
chmod u+x wrf_install
./wrf_install
```

若安装 **WRF-Chem** , 执行命令:

```bash
bash wrf_install -chem
```

或

```bash
chmod u+x wrf_install
./wrf_install -chem
```

若安装 **WRF-Hydro** , 执行命令:

```bash
bash wrf_install -hydro
```

或

```bash
chmod u+x wrf_install
./wrf_install -hydro
```

在安装过程中，WRF 与 WPS 编译所需的包（除 mpich）会采用 conda 进行安装。如果没有安装 conda，该脚本会自动安装 Miniconda，相关包默认会安装在名为 “WRF” 的环境中，你可以在运行脚本时更改 Miniconda 安装位置与环境的名称。mpich 会安装在 “./Build_WRF/mpich” 中。

WRF 与 WPS 会通过 git clone 从官方仓库下载，如果你的网络并不稳定，你可以尝试多运行几次或者手动下载它们放置在安装目录中（请确保目录名为 “WRF” 和 “WPS”）。

默认情况下，该脚本会选择 WRF 的 ‘dmpar’ 模式、基础的嵌套模式、WPS 的 ‘serial’ 模式，如果你有特别的需求，请修改脚本开头的  `WRF_config1` 、`WRF_config2`  、`WPS_config` 变量的值。

