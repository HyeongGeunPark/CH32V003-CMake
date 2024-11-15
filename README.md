# CH32V003 template for vscode (on windows)

## Requirements
- vscode extensions
    - [Peripheral Viewer](https://marketplace.visualstudio.com/items?itemName=mcu-debug.peripheral-viewer)
- ToolChain from MounRiver Studio (or MRS Community)

## Detail
- This template uses vscode's tasks.json file to run various commands.
    - Since cmake-tools currently does not support gdbserver connection, there is no choice.
- Read tasks.json to see what happens inside

## How to use
- Specify your environment in these files
    - /.vscode/settings.json
        - These variables are used in tasks.json and launch.json
        - read your_settings.json for more information
    - /CMakeLists.txt
        - set "TOOLPATH" to your toolchain directory
- Press F5 to run debug
- Other tasks are registered in tasks.json, so you can run those tasks with Ctrl+Shift+P -> tasks -> \[task name\]

## Note
- All tasks assumes that the default shell is PWSH.

--------------------------------------------------------------
README.md from original repository
--------------------------------------------------------------
# CH32V003-CMake

摆脱eclipse编译环境，使用vscode编辑代码。

此仓库为cmake模板，请根据自己的工程进行适当修改。

请在CmakeLists.txt文件内更改`TOOLPATH`的变量为你的工具链路径。

```shell
A和B方法任选其一即可

A、使用cmake生成eclipse Makefile工程
cmake -G"Eclipse CDT4 - Unix Makefiles" ..
如果没有把make.exe加入系统path:
cmake -G"Eclipse CDT4 - Unix Makefiles" -D"你的路径/make.exe"  ..

B、使用cmake生成ninja工程
cmake -G"Ninja" ..
如果没有把ninja.exe加入系统path:
cmake -G"Ninja" -D"你的路径/ninja.exe" ..
```

