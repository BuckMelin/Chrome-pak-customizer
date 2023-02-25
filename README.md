# chrome-pak-customizer
一个简单的批处理工具，用于在Chrome或基于铬的浏览器中自定义Pak文件

## Badges
[![Build status](https://ci.appveyor.com/api/projects/status/4ji3guqh4yyjfiaa?svg=true)](https://ci.appveyor.com/project/myfreeer/chrome-pak-customizer)
[![Download](https://img.shields.io/github/downloads/myfreeer/chrome-pak-customizer/total.svg)](https://github.com/myfreeer/chrome-pak-customizer/releases)
[![Latest Release](https://img.shields.io/github/release/myfreeer/chrome-pak-customizer.svg)](https://github.com/myfreeer/chrome-pak-customizer/releases/latest)

## 许可证
* Windows构建默认获得许可，可以通过附加到cmake来禁用。LGPL 2.1+-DLGPL=OFF
* 非 Windows 版本和具有 WITH 的构建均获得 MIT 许可。-DLGPL=OFF

## 用法（仅 Windows）
1.从版本下载并将其解压缩到任何文件夹。chrome-pak.7z
2.将 pak 文件拖放到 .unpack.bat
3.该 pak 文件将被解压缩到 pak 文件的文件夹的子文件夹中， 与带有后缀的 pak 文件同名。_unpacked
4.（可选）修改提取的文件。
5.拖动到 。pak_index.inipack.bat
6.重新打包的 pak 文件将位于名称为 的同一文件夹中。pak_index.inipak_index_packed.pak

There is also a [GIF Guide](https://github.com/myfreeer/chrome-pak-customizer/wiki/GIF-Guide-v2) on windows.

## Usage (Command line)
```
pak.exe -u pak_file destination_path
Unpack chrome pak file at pak_file to destination_path.

pak.exe -p pak_index_file destination_pak_file
Pack chrome pak file using pak_index_file to destination_pak_file.
pak_index_file would be found in unpacked path.

Note: existing destination files would be overwritten
```

## Building
### Prerequires
* gcc
* cmake
* ninja

### Build script example
```bash
# Getting source
git clone https://github.com/myfreeer/chrome-pak-customizer --branch=develop --single-branch
cd chrome-pak-customizer

# Creating folder for build
mkdir -p build
cd build

# Running cmake
cmake -GNinja -DLGPL=OFF ..

# Building
ninja
```
### CMake options
* `LGPL`: Enable LGPL 2.1+ licensed custom startfiles on windows for smaller binary

## Credits
* <https://www.chromium.org/>
* <https://github.com/shuax/ChromePAK>
* <https://github.com/myfreeer/win-startup-headers>
