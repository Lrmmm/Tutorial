# Vscode调试配置
```json
{
    
    "version": "0.2.0",
    "configurations": [
        {   //出现在vscode界面上的名字
            "name": "(gdb) 启动",
            // debugger类型 这是gdb
            "type": "cppdbg",
            "request": "launch",
             //可执行文件位置
            "program": "${workspaceFolder}/xxx/yyy",
            "args": [],
            //是否进入后暂停
            "stopAtEntry": false,
            //工作目录
            "cwd": "${workspaceFolder}/xxx",
            "environment": [],
             //是否使用外部终端
            "externalConsole": false,
             // dubug之前要运行的任务
            //"preLaunchTask": "Build Fortran", 
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
                {
                    "description":  "将反汇编风格设置为 Intel",
                    "text": "-gdb-set disassembly-flavor intel",
                    "ignoreFailures": true
                }
            ],
            // debug程序位置 gdb的位置
            "miDebuggerPath": "/usr/bin/gdb", 
        },
    ]
}
```
