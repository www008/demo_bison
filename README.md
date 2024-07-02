# Bison&Flex生成C++样例(CMake版)

## 特点

* Bison&Flex的C++源码生成
* VSCode中MinGW编译

**注**:  
原项目来自[C++版PDDL解析器](https://github.com/thiagopbueno/pddlparser-pp)  

## 安装步骤

* VSCode下安装MinGW编译环境
    需安装MYSYS2[参阅](https://code.visualstudio.com/docs/cpp/config-mingw)

* MYSYS2中安装Bison&Flex包
    打开ucrt64控制台，执行

    ```shell
    # pacman -S Bison
    # pacman -S Flex
    ```

* 系统环境变量Path
    添加gcc路径：`D:\Program Files\msys64\ucrt64\bin`
    添加bison、flex路径：`D:\Program Files\msys64\usr\bin`

**注**:不要在MYSYS2中安装CMake，否则该cmake会在vscode中执行并失败

## 测试

```shell
# build\PDDLParse\bin\PDDLParser.exe  data/gripper.pddl data/gripper-4.pddl
```
