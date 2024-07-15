# Script for Installing WRF

[[中文]](./README_zh.md)

This script installs the Weather Research and Forecasting (WRF) model automatically without requiring root privileges. It is based on the script provided by [Umur Dinç](https://github.com/bakamotokatas/WRF-Install-Script).

## Prerequisites

Before installation, please ensure the following packages are installed on your system:

- csh
- wget
- essential tools for building

## Installation

Place “wrf_install” in the directory where you want WRF and WPS to be installed.

For the **default model (WRF-ARW)**, run:

```bash
bash wrf_install
```

or

```bash
chmod u+x wrf_install
./wrf_install
```

For **WRF-Chem** , run:

```bash
bash wrf_install -chem
```

or

```bash
chmod u+x wrf_install
./wrf_install -chem
```

For **WRF-Hydro** , run:

```bash
bash wrf_install -hydro
```

or

```bash
chmod u+x wrf_install
./wrf_install -hydro
```

During the installation, necessary packages (except mpich) for compiling WRF and WPS will be installed with conda. If conda is not available on your system, the script will install Miniconda for you. The default environment for installing necessary packages is named “WRF,” but you can rename it when running the script. The `mpich` package will be installed in “./Build_WRF/mpich” by compilation.

WRF and WPS will be downloaded via git clone from the official repository. If your network is unstable, you can re-run the script or manually download the repository and place it in your installation directory (ensure their names are “WRF” and “WPS”).

By default, this script will choose the ‘dmpar’ mode for WRF, basic type of nesting, and the ‘serial’ mode for WPS. If you have specific requirements, please modify the `WRF_config1`, `WRF_config2`, and `WPS_config` variables at the beginning of the script.

Under normal circumstances, you only need to verify the conda installation path and the environment name. The rest of the installation process is automated.

