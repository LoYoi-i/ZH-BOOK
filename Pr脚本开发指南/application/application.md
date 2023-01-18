应用对象
==================

``app``

**描述**
提供对 Premiere Pro 中对象和应用程序设置的访问.
单个全局对象始终可以通过其名称获得, **app**.

==========
Attributes 属性
==========

``app.anywhere``

**描述**
`anywhere`, 提供对可用 Anywhere 服务器的访问。仅在 Anywhere 配置中运行时可用（已停产）.

**类型**
`anywhere`.

*********************************************
``app.build``

**描述**
正在运行的 Premiere Pro 版本号。

**类型**
字符串; 只读.

**示例**
获取当前应用程序的构建版本 *（Adobe Premiere Pro 版本 14.3.1（构建 45））*

    parseInt(app.build); // 45

*********************************************
``app.encoder``

**描述**
提供对 Adobe Media Encoder（在同一系统上）的访问。
Warning: app.encoder is broken on Premiere Pro 14.3.1 - 15 on Mac only. Fixed in 22 and up.
https://community.adobe.com/t5/premiere-pro-discussions/missing-the-object-app-encoder-14-3-1-15-0-15-1-15-2/m-p/12544488

**类型**
`encoder`.

*********************************************
``app.getAppPrefPath``

**描述**
包含当前活动的“Adobe Premiere Pro Prefs”文件的路径。

**类型**
字符串; 只读.

**示例**
获取当前活动首选项文件的路径


    app.getAppPrefPath; // /Users/USERNAME/Documents/Adobe/Premiere Pro/14.0/Profile-USERNAME/

*********************************************

``app.getAppSystemPrefPath``

**描述**
Premiere Pro 的活动配置文件，不特定于给定用户。

**类型**
字符串; 只读.

**示例**
获取当前活动配置文件夹的路径

    app.getAppSystemPrefPath; // /Library/Application Support/Adobe/Adobe Premiere Pro 2020/

*********************************************
``app.getPProPrefPath``

**描述**
包含当前活动的“Adobe Premiere Pro Prefs”文件的路径。

**类型**
字符串; 只读.

**示例**
获取当前活动首选项文件的路径

    app.getPProPrefPath; // /Users/USERNAME/Documents/Adobe/Premiere Pro/14.0/Profile-USERNAME/

*********************************************
``app.getPProSystemPrefPath``

**描述**
Premiere Pro 的活动配置文件，不特定于给定用户。

**类型**
字符串; 只读.

**示例**
获取当前活动配置文件夹的路径

    app.getPProSystemPrefPath; // /Library/Application Support/Adobe/Adobe Premiere Pro 2020/

*********************************************
``app.learnPanelContentDirPath``

**描述**
获取学习面板的内容目录路径。

**类型**
字符串; 只读.

**示例**
获取学习面板目录的路径

    app.learnPanelContentDirPath; // /Users/Shared/Adobe/Premiere Pro 2020/Learn Panel/

*********************************************
``app.learnPanelExampleProjectDirPath``

**描述**
获取学习面板的示例项目目录路径。

**类型**
字符串; 只读.

**示例**
获取学习面板示例项目目录的路径

    app.learnPanelExampleProjectDirPath; // /Users/Shared/Adobe/Premiere Pro/14.0/Tutorial/Going Home project/

*********************************************
``app.metadata``

**描述**
获取应用程序元数据对象。

**类型**
`metadata`, 只读.

*********************************************
``app.path``

**描述**
获取应用程序可执行文件的路径。

**类型**
字符串; 只读.

**示例**
获取应用程序可执行文件的路径。
    app.path; // /Applications/Adobe Premiere Pro 2020/Adobe Premiere Pro 2020.app/

*********************************************
``app.production``

**描述**
目前积极生产。

**类型**
`production` 如果至少有 1 个生产是开放的, ``null`` 否则.

*********************************************
``app.project``

**描述**

当前活动的项目。

**类型**
`project`.

*********************************************
``app.projectManager``

**描述**

提供对 Premiere Pro 中项目管理功能的访问。

**类型**
`projectManager`.

*********************************************
``app.projects``

**描述**
引用所有打开项目的数组； ``numProjects`` 包含大小。

**类型**

`projectCollection`, 只读.


*********************************************
``app.properties``

**描述**
属性对象提供访问和修改首选项值的方法。

**类型**
`properties`, 只读;

*********************************************
``app.sourceMonitor``

**描述**
提供访问 : `sourceMonitor`.

**类型**
`sourceMonitor`.


*********************************************
``app.userGuid``

**描述**

当前登录的 Creative Cloud 用户的唯一标识符。

**类型**

字符串; 只读.

*********************************************

``app.version``

**描述**
Premiere Pro 的版本，提供 API。

**类型**
字符串; 只读.

**示例**
获取当前应用程序的版本 *（Adobe Premiere Pro 版本 14.3.1 (Build 45))*
    app.version; // 14.3.1

==============
# Methods 方法

*********************************************
``app.enableQE()``

**描述**
启用 Premiere Pro 的 QE DOM。

**Parameters 参数**
None.

**Returns 返回**
如果启用了 QE DOM，则返回 true。

*********************************************
``app.getEnableProxies()``

**描述**
确定当前是否启用代理使用。

**Parameters 参数**
None.

**Returns 返回**
如果启用了代理，则返回 1，否则返回 0。

*********************************************
``app.getWorkspaces()``

**描述**
获取可用工作区数组作为字符串。

**Parameters 参数**
None.

**Returns 返回**
``Array`` 如果成功, ``null`` 如果不成功.

**示例**
获取可用工作区的列表。

    app.getWorkspaces();
     [
        "All Panels",
        "Assembly",
        "Audio",
        "Color",
        "Editing",
        "Effects",
        "Graphics",
        "Learning",
        "Libraries",
        "Metalogging",
        "Production"
    ];

*********************************************
``app.isDocument(path)``

**描述**
确定路径中的文件是否可以作为 Premiere Pro 打开 : `project <project>`.

**Parameters 参数**

| 参数 | 类型       | 描述       |
| -------- | ---------- | ----------------- |
| ``path`` | ``String`` | 文件路径. |


**Returns 返回**
返回 **true** 文件是否可以作为 Premiere Pro 打开 : `project <project>`.

**示例**
测试有效的项目文件

    app.isDocument('~/Desktop/myProject.prproj'); // true
    app.isDocument('~/Desktop/textFile.txt');     // false
    app.isDocument('~/Desktop/footageFile.mov');  // false
    app.isDocument('~/Desktop/imageFile.mov');    // false

*********************************************
``app.isDocumentOpen()``

**描述**
判断是否有 :`projects <project>` 目前开放.

**Parameters 参数**
None.

**Returns 返回**
Returns **true** 如果至少有 1 个项目是开放的；否则 **false**.

*********************************************
``app.newProject(path)``

**描述**
Creates a new .prproj :ref:`project`, at the specified path.

**Parameters 参数**
| Argument | Type       | Description                                                                  |
| -------- | ---------- | ---------------------------------------------------------------------------- |
| ``path`` | ``String`` | A full path to new project; a .prproj extension will be added, if necessary. |


**Returns 返回**
Returns **true** if successful.


***********************
``app.openDocument(path)``

**描述**
Opens the file at the specified path, as a Premiere Pro :ref:`project`.
**Parameters 参数**
| Argument                     | Type        | Description                                                     |
| ---------------------------- | ----------- | --------------------------------------------------------------- |
| ``path``                     | ``String``  | 要打开的文档的完整路径。                         |
| ``suppressConversionDialog`` | ``Boolean`` | 可选，禁止项目转换对话框。               |
| ``bypassLocateFileDialog``   | ``Boolean`` | 可选，绕过定位文件对话框.                        |
| ``bypassWarningDialog``      | ``Boolean`` | 可选，绕过警告对话框.                                |
| ``doNotAddToMRUList``        | ``Boolean`` | 可选，跳过将此文件添加到最近使用列表. |

**Returns 返回**
Returns **true** 如果文件被成功打开.

*********************************************
``app.openFCPXML(path, projPath)``

**描述**
将 FCP XML 文件作为 Premiere Pro 打开 :`project` (在 projPath 中指定).

**Parameters 参数**
| Argument | Type | Description |
| -------- | ---- | ----------- |
``path``          ``String``   
``projPath``      ``String``   

**Returns 返回**
Returns **true** 如果文件作为 Premiere Pro 成功打开 :`project`.

*********************************************
``app.quit()``

**描述**
退出 Premiere Pro；系统将提示用户保存对 :`project`.

**Parameters 参数**
None.

**Returns 返回**
Nothing.

*********************************************
``app.setEnableProxies(enabled)``

**描述**
确定当前是否启用代理使用。

**Parameters 参数**

| Argument    | Type        | Description                                   |
| ----------- | ----------- | --------------------------------------------- |
| ``enabled`` | ``Integer`` | ``1`` 打开代理, ``0`` 关掉它们. |


**Returns 返回**
如果代理启用已更改，则返回 1.

************************************************;
``app.setExtensionPersistent(extensionID, persistent)``

**描述**
在此会话中，具有给定 extensionID 的扩展是否持续存在.

**Parameters 参数**
| Argument        | Type        | Description                                                       |
| --------------- | ----------- | ----------------------------------------------------------------- |
| ``extensionID`` | ``String``  | Which extension to modify.                                        |
| ``persistent``  | ``Integer`` | Pass ``1`` to keep extension in memory, ``0`` to allow unloading. |

**Returns 返回**
Returns **true** 如果成功. 

**示例**

    var extensionID = 'com.adobe.PProPanel';
    // 0 - while testing (to enable rapid reload);
    // 1 - for "Never unload me, even when not visible."
    var persistent = 0;

    app.setExtensionPersistent(extensionID, persistent);

*********************************************
``app.setScratchDiskPath(path, scratchDiskType)``

**描述**
指定用于 Premiere Pro 的暂存盘路径之一的路径.

**Parameters 参数**
| Argument            | Type       | Description                                                                                                                                                                                                                                                                                                                                                       |
| ------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``path``            | ``String`` | 要使用的新路径.                                                                                                                                                                                                                                                                                                                                          |
| ``scratchDiskType`` | ``Enum``   | 枚举值，必须是以下之一:  ``ScratchDiskType.FirstVideoCaptureFolder``  ``ScratchDiskType.FirstAudioCaptureFolder`` ``ScratchDiskType.FirstVideoPreviewFolder`` ``ScratchDiskType.FirstAudioPreviewFolder`` ``ScratchDiskType.FirstAutoSaveFolder``  ``ScratchDiskType.FirstCCLibrariesFolder`` ``ScratchDiskType.FirstCapsuleMediaFolder`` |


**Returns 返回**
Returns 'true' if successful.

**示例**

    var scratchPath = Folder.selectDialog('Choose new scratch disk folder');
    if (scratchPath && scratchPath.exists) {
        app.setScratchDiskPath(scratchPath.fsName, ScratchDiskType.FirstAutoSaveFolder);
    }
    
*********************************************
``app.setSDKEventMessage(message, decorator)``

**描述**
将字符串写入 Premiere Pro 的事件面板.

**Parameters 参数**
| Argument      | Type       | Description                                                |
| ------------- | ---------- | ---------------------------------------------------------- |
| ``message``   | ``String`` | 要显示的消息.                                      |
| ``decorator`` | ``String`` | 枚举之一:    ``info``    ``warning``    ``error`` |

**Returns 返回**
如果成功则返回“真”.

*********************************************
``app.setWorkspace(workspace)``

**描述**
将工作区设置为活动。利用 :`app.getWorkspaces` 获取所有可用工作区的列表.

**Parameters 参数**
| Argument      | Type       | Description                |
| ------------- | ---------- | -------------------------- |
| ``workspace`` | ``String`` | 工作区的名称. |

**Returns 返回**
``Boolean``.

**示例**
启用 ``Editing`` 工作区.

    var workspace = 'Editing';
    if (app.setWorkspace(workspace)) {
        alert('Workspace changed to "' + workspace + '"');
    } else {
        alert('Could not set "' + workspace + '" workspace');
    }

*********************************************
``app.trace()``

**描述**
将字符串写入 Premiere Pro 的调试控制台.

**Parameters 参数**
None.

**Returns 返回**
Returns **true** 如果添加了跟踪.


*********************************************
``app.getProjectViewIDs()``

**描述**
返回与任何项目关联的当前打开视图的视图 ID.

**Parameters 参数**
None.

**Returns 返回**
一组视图 ID；可以为空.

**示例**

    var allViewIDs = app.getProjectViewIDs();
    if (allViewIDs){
        var firstOne = allViewIDs[0];
    } else {
        // No views open.
    }


*********************************************
``app.getProjectFromViewID()``

**描述**
返回与提供的视图 ID 关联的项目.

**Parameters 参数**
视图 ID，获取自 ``getProjectViewIDs``. 

**Returns 返回**
一个 Project 对象，用于与提供的视图 ID 关联的项目。可 ``null``.

**示例**

    var allViewIDs = app.getProjectViewIDs();
    if (allViewIDs){
        var firstOne = allViewIDs[0];
        if (firstOne){
            var thisProject = getProjectFromViewID(firstOne);
            if (thisProject){
                var name = thisProject.name;
            } else {
                // no project associated with that view ID.
            }
    } else {
        // No views open.
    }

*********************************************

``app.getCurrentProjectViewSelection()``

**描述**
返回在当前活动项目视图中选择的项目项数组.

**Parameters 参数**
None.

**Returns 返回**
一组项目项；可以为空.

**示例**

    var selectedItems = app.getCurrentProjectViewSelection();
    if (selectedItems){
        var firstOne = selectedItems[0];
    } else {
        // No projectItems selected.
    }
