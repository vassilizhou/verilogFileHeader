## 安装 koroFilleHeader 
- 在VsCode Extension中，搜索koroFileHeader，安装即可

## 修改 settings.json
- 在VsCode界面中，输入**Ctrl+Shift+P**
- 输入settings
- 选择 **Preference: Open User Settings (JSON)** 即可打开settings.json
- 假设原始settings.json内容如下
```json
{
    "workbench.colorTheme": "Default Light+",
    "files.watcherExclude": {
        "**/.bloop": true,
        "**/.metals": true,
        "**/.ammonite": true
    }
}
```
- 打开本目录下的settings.json，注释标注了fileheader相关设置的范围，共包含 **fileheader.customMade**, **fileheader.cursorMode**, **fileheader.configObj** 三项
```json

    // ==  Add Fileheader Settings Below to Your settings.json ==
    "fileheader.customMade": {
      xxxxxx
    },
    "fileheader.cursorMode": {
      xxxxxx
    },
    "fileheader.configObj": {
      xxxxxx
    }

    // == Fileheader Settings End Here, Mind the "}" and "," ==

```
- 将上述三项配置添加到你的settings.json中。修改后的 settings.json应包含如下内容
```json
{
    // 你的原始内容
    "workbench.colorTheme": "Default Light+",
    "files.watcherExclude": {
        "**/.bloop": true,
        "**/.metals": true,
        "**/.ammonite": true
    },
    // 新添加的fileHeader设置
    "fileheader.customMade": {
      xxxxxx
    },
    "fileheader.cursorMode": {
      xxxxxx
    },
    "fileheader.configObj": {
      xxxxxx
    }
}
```

## Tips
- 按理来说VsCode会自动插入文件头。当自动插入不生效时，使用 **Ctrl+Win+i** 手动插入
- 有时VsCode抽风，会在已经有文件头的文件中宠物插入文件头，手动删除即可
- 文件头 **自动插入Author** 的功能需**配合git食用**，即，确保你使用VsCode的环境中 **已安装git** 且完成 **user.name** 和 **user.email** 的配置。具体地：
> - 如果你使用WSL以Remote方式启动VsCode，确保WSL环境下安装有git且完成配置
> - 如果你使用Windows直接启动VsCode，确保安装了git bash并在其中完成配置

## 挖坑
- bat脚本自动更新settings.json
- fileHeader自动获取parameter与io列表