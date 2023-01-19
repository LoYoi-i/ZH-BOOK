# Project object
``app.project``

**描述**
表示Premiere Pro项目。从Premiere Pro 12.0开始，可能会同时打开多个项目。

----

# Attributes 属性

----
## Project.activeSequence
``app.project.activeSequence``

**描述**
项目中当前活动的`序列`。

**类型**
一个`序列`，如果当前没有序列处于活动状态，则为`0`。

----
## Project.cloudProjectlocalID
``app.project.cloudProjectlocalID``

**描述**
云项目的ID。

**类型**
String; 读/写.

----
## Project.documentID
``app.project.documentID``

**描述**
此项目的唯一标识符，格式为 ``xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx``.

**类型**
String; 只读.

----
## Project.isCloudProject
``app.project.isCloudProject``

**描述**
检查项目是否为云项目。

**类型**
Boolean; 只读.

----
## Project.name-
``app.project.name``

**描述**
项目的名称。

**类型**
String; 只读.

----
## Project.path
``app.project.path``

**描述**
项目的文件路径。

**类型**
String; 只读.

**示例**
获取当前活动项目的路径

    app.project.path; // /Users/USERNAME/Desktop/Project.prproj

----
## Project.rootItem
``app.project.rootItem``

**描述**
表示项目`根`的`projectItem`。

**类型**
一个 `projectItem`； 这将始终是 ``ProjectItemType_BIN`` 类型。

----
## Project.sequences
``app.project.sequences``

**描述**
项目中的序列。

**类型**
`sequenceCollection`, 只读.

----

# Methods 方法

----
## Project.addPropertyToProjectMetadataSchema()
``app.project.addPropertyToProjectMetadataSchema(propertyName, propertyLabel, propertyType)``

**描述**
将指定类型的新字段添加到Premiere Pro的私有项目元数据架构中。

**参数**

| 参数              | 类型       | 描述                                                                                     |
| ----------------- | ---------- | ---------------------------------------------------------------------------------------- |
| ``propertyName``  | ``String`` | 要添加的属性的名称。                                                                     |
| ``propertyLabel`` | ``String`` | 要添加的属性标签。                                                                       |
| ``propertyType``  |            | 必须是以下之一：<br>- 0 ``Integer``<br>- 1 ``Real``<br>- 2 ``String``<br>- 3 ``Boolean`` |


**返回**
如果成功，返回**true**；如果失败，返回**undefined**。

----
## Project.closeDocument()
``app.project.closeDocument(saveFirst, promptIfDirty)``

**描述**
关闭此项目。

**参数**

| 参数              | 类型        | 描述                                      |
| ----------------- | ----------- | ----------------------------------------- |
| ``saveFirst``     | ``Integer`` | 如果为`1`，则项目将在关闭前保存。         |
| ``promptIfDirty`` | ``Integer`` | 如果`1`，系统将询问用户是否要先保存更改。 |


**返回**
如果成功则返回**0**。

----
## Project.consolidateDuplicates()
``app.project.consolidateDuplicates()``

**描述**
调用Premiere Pro的“合并重复视频”功能（可从UI获得）。

**参数**
无.

**返回**
如果成功，则返回**0**。

----
## Project.createNewSequence()
``app.project.createNewSequence(sequenceName, sequenceID)``

**描述**
使用指定的ID创建新的`序列`。

**参数**
| 参数             | 类型       | 描述                 |
| ---------------- | ---------- | -------------------- |
| ``sequenceName`` | ``String`` | 序列的名称。         |
| ``sequenceID``   | ``String`` | 新序列的唯一标识ID。 |

**返回**
如果创建成功，则返回`序列`；如果创建失败，则返回**0**。

----
## Project.createNewSequenceFromClips()
``app.project.createNewSequenceFromClips(sequenceName, arrayOfProjectItems, destinationBin);``

**描述**
在指定的目标bin中创建具有给定名称的新`sequence序列`，并将项目项依次插入其中。

**参数**

| 参数                    | 类型                                     | 描述                                  |
| ----------------------- | ---------------------------------------- | ------------------------------------- |
| ``sequenceName``        | ``String``                               | 可选择的新序列的名称。                |
| ``arrayOfProjectItems`` | ``Array`` of `ProjectItem <projectItem>` | objects要插入到序列中的项目项的数组。 |
| ``destinationBin``      | `projectItem`                            | 可选择的包含序列的容器。              |

**返回**
如果成功，则返回新创建的`序列`如果失败，则返回“0”。

----
## Project.deleteSequence()
``app.project.deleteSequence(sequence)``

**描述**
从项目中删除指定的`序列`。

**参数**

| 参数         | 类型       | 描述           |
| ------------ | ---------- | -------------- |
| ``sequence`` | `sequence` | 要删除的序列。 |


**返回**
如果成功，则返回0.

----
## Project.exportAAF()
``app.project.exportAAF(sequenceToExport, outputPath, mixdownVideo, explodeToMono, sampleRate, bitsPerSample, embedAudio, audioFileFormat, trimSources, handleFrames, presetPath, renderAudioEffects, includeClipCopies, preserveParentFolder)``

**描述**
使用指定的设置导出指定1序列`的AAF文件。

**参数**

| 参数                     | 类型        | 描述                                                       |
| ------------------------ | ----------- | ---------------------------------------------------------- |
| ``sequenceToExport``     | `sequence`  | 要导出的序列。                                             |
| ``outputPath``           | ``String``  | .aaf文件的输出路径。                                       |
| ``mixdownVideo``         | ``Integer`` | 如果`1`，则在导出之前渲染视频。                            |
| ``explodeToMono``        | ``Integer`` | 如果为`1`，则将立体声音轨拆分为单声道。                    |
| ``sampleRate``           | ``Integer`` | 输出音频的采样率。                                         |
| ``bitsPerSample``        | ``Integer`` | 音频输出的每个采样位数。                                   |
| ``embedAudio``           | ``Integer`` | 如果为`1`，则嵌入音频；如果为`0`，则为外部。               |
| ``audioFileFormat``      | ``Integer`` | `0`是AIFF，`1`是WAV。                                      |
| ``trimSources``          | ``Integer`` | 如果为`1`，则在导出之前修剪并重新编码媒体`0`导出整个文件。 |
| ``handleFrames``         | ``Integer`` | 控制柄帧数（从0到1000）。                                  |
| ``presetPath``           | ``String``  | 导出预设（.epr）文件的路径。                               |
| ``renderAudioEffects``   | ``Integer`` | 如果为`1`，则在导出前渲染音频效果。                        |
| ``includeClipCopies``    | ``Integer`` | 如果是`1`，请包含剪辑的每个副本。                          |
| ``preserveParentFolder`` | ``Integer`` | 如果`1`，则在输出中保留父文件夹。                          |

**返回**
如果成功则返回**0**。

----
## Project.exportFinalCutProXML()
``app.project.exportFinalCutProXML(outputPath, suppressUI)``

**描述**
将整个项目的FCP XML表示导出到指定的输出路径。

**参数**

| 参数           | 类型        | 描述                                            |
| -------------- | ----------- | ----------------------------------------------- |
| ``outputPath`` | ``String``  | .xml文件的输出路径。                            |
| ``suppressUI`` | ``Integer`` | 如果`1`，则在导出过程中不会显示任何警告或警报。 |

**返回**
如果成功，则返回0.

----
## Project.exportOMF()
``app.project.exportOMF(sequence, outputPath, omfTitle, sampleRate, bitsPerSample, audioEncapsulated, audioFileFormat, trimAudioFiles, handleFrames, includePan)``

**描述**
使用指定的设置导出指定`序列`的OMF文件。

**参数**

| 参数                  | 类型        | 描述                                         |
| --------------------- | ----------- | -------------------------------------------- |
| ``sequence``          | `sequence`  | 要输出的序列。                               |
| ``filePath``          | ``String``  | .omf文件的输出路径。                         |
| ``omfTitle``          | ``String``  | OMF的标题。                                  |
| ``sampleRate``        |             | 输出音频的采样率。                           |
| ``bitsPerSample``     |             | 音频输出的每个采样位数。                     |
| ``audioEncapsulated`` | ``Integer`` | 如果为`1`，则嵌入音频；如果为`0`，则为外部。 |
| ``audioFileFormat``   | ``Integer`` | ``0`` 是 AIFF, ``1`` 是 WAV.                 |
| ``trimAudioFiles``    | ``Integer`` | `1`表示是，修剪音频文件。                    |
| ``handleFrames``      | ``Integer`` | 手柄框架的数量（从0到1000）。                |
| ``includePan``        | ``Integer`` | `1`表示包含泛信息`0`表示不。                 |

**返回**
如果成功则返回**0**。

----
## Project.exportTimeline()
``app.project.exportTimeline(exportControllerName)``

**描述**
使用具有指定名称的导出控制器插件导出当前活动的`序列`。

**参数**

| 参数                     | 类型       | 描述                                                                                       |
| ------------------------ | ---------- | ------------------------------------------------------------------------------------------ |
| ``exportControllerName`` | ``String`` | 要使用的导出控制器插件的名称。要使用Premiere Pro SDK示例导出控制器，值应为“SDK导出控制器”. |


**返回**
如果成功，则返回**0**，否则返回错误代码。

----
## Project.getGraphicsWhiteLuminance()
``app.project.getGraphicsWhiteLuminance();``

**描述**
检索此项目的当前图形白亮度值。

**参数**
无.

**返回**
返回当前选定的图形白值。

----
## Project.getInsertionBin()
``app.project.getInsertionBin()``

**描述**
返回一个`projectItem`，该项目引用将进行导入的bin。

**参数**
无.

**返回**
如果成功，返回`projectItem`；如果不成功，则返回**0**。

----
## Project.getProjectPanelMetadata()
``app.project.getProjectPanelMetadata()``

**描述**
返回“项目”面板的当前布局。

**参数**
无.

**返回**
返回表示当前Project面板布局的**字符串**，如果不成功，则返回**0**。

----
## Project.getSharedLocation()
``app.project.getSharedLocation()``

**描述**
返回共享文件要复制到的位置的路径。

**参数**
无.

**返回**
返回包含路径的**字符串**。

----
## Project.getSupportedGraphicsWhiteLuminances()
``app.project.getSupportedGraphicsWhiteLuminances();``

**描述**
检索此项目支持的图形白亮度值。

**参数**
无.

**返回**
返回项目支持的图形白色设置数组；目前它返回（100、203、300）

----
## Project.importAEComps()
``app.project.importAEComps(path, compNames, targetBin)``

**描述**
从包含After Effects.aep项目文件中导入指定的合成（按名称）。您可以在包含项目中指定目标bin；否则，组合将出现在该项目中最近的目标bin中。

**参数**

| 参数          | 类型          | 描述                              |
| ------------- | ------------- | --------------------------------- |
| ``path``      | ``String``    | After Effects.aep项目文件的路径。 |
| ``compNames`` | ``Array``     | 指定项目中要导入的组成的名称。    |
| ``targetBin`` | `projectItem` | 可选择的此导入的目标仓位。        |

**返回**
如果成功则返回**0**。

----
## Project.importAllAEComps()
``app.project.importAllAEComps(path, targetBin)``

**描述**
从包含After Effects.aep项目文件中导入指定的合成（按名称）。您可以在包含项目中指定目标bin；否则，组合将出现在该项目中最近的目标bin中。

**参数**

| 参数          | 类型          | 描述                              |
| ------------- | ------------- | --------------------------------- |
| ``path``      | ``String``    | After Effects.aep项目文件的路径。 |
| ``targetBin`` | `projectItem` | 可选择的此导入的目标仓位。        |

**返回**
如果成功则返回**0**。

----
## Project.importFiles()
``app.project.importFiles(filePaths, suppressUI, targetBin, importAsNumberedStills)``

**描述**
Imports media from the specified file paths.

**参数**

| 参数                       | 类型          | 描述                                   |
| -------------------------- | ------------- | -------------------------------------- |
| ``filePaths``              | ``Array``     | 要导入的文件路径的数组。               |
| ``suppressUI``             | ``Boolean``   | 是否应抑制警告对话框。                 |
| ``targetBin``              | `projectItem` | 应将文件导入的bin。                    |
| ``importAsNumberedStills`` | ``Boolean``   | 文件路径是否应解释为一系列编号的剧照。 |

**返回**
Returns **true** if successful, **false** if not.

----
## Project.importSequences()
``app.project.importSequences(path, sequenceIDs)``

**描述**
将指定项目中的`sequence <sequence>`对象（具有指定的 sequenceID）数组导入当前项目。

**参数**

| 参数            | 类型       | 描述                 |
| --------------- | ---------- | -------------------- |
| ``path``        | ``String`` | 项目文件的路径。     |
| ``sequenceIDs`` | ``Array``  | 要导入的序列ID数组。 |

**返回**
如果成功则返回**0**。

----
## Project.isSharedLocationCopyEnabled()
``app.project.isSharedLocationCopyEnabled()``

**描述**
确定是否为此项目启用复制到共享位置。

**参数**
无.

**返回**
如果启用复制，则返回**true**,否则为**false**。

----
## Project.newBarsAndTone()
``app.project.newBarsAndTone(width, height, timeBase, PARNum, PARDen, audioSampleRate, name)``

**描述**
基于指定的预设（.sqpreset文件）创建具有给定名称的新`序列`。

**参数**

| 参数                | 类型        | 描述                 |
| ------------------- | ----------- | -------------------- |
| ``width``           | ``Integer`` | 宽                   |
| ``height``          | ``Integer`` | 高                   |
| ``timeBase``        |             | 新项目项的时间基准。 |
| ``PARNum``          | ``Integer`` | 像素纵横比分子。     |
| ``PARDen``          | ``Integer`` | 像素纵横比分母。     |
| ``audioSampleRate`` |             | 音频采样率。         |
| ``name``            | ``String``  | 新项目项的名称。     |

**返回**
返回新条形图和色调的`projectItem`，如果不成功，则返回**0**。

----
## Project.newSequence()
``app.project.newSequence(name, pathToSequencePreset)``

**描述**
基于指定的预设（.sqpreset文件）创建具有给定名称的新`序列`。

**参数**

| 参数                     | 类型       | 描述                      |
| ------------------------ | ---------- | ------------------------- |
| ``name``                 | ``String`` | 新序列的名称。            |
| ``pathToSequencePreset`` | ``String`` | 预设.sqpreset文件的路径。 |

**返回**
Returns a `sequence`, or **0** if unsuccessful.

----
## Project.openSequence()
``app.project.openSequence(sequence.sequenceID)``

**描述**
使用提供的序列ID激活`序列`。这将在时间线面板中打开序列。

**参数**

| 参数           | 类型                  | 描述                 |
| -------------- | --------------------- | -------------------- |
| ``sequenceID`` | `sequence.sequenceID` | 应打开的有效序列ID。 |

**返回**
如果成功，则返回**true**，否则返回**false**。

----
## Project.pauseGrowing()
``app.project.pauseGrowing(pause)``

**描述**
暂停（并恢复）不断增长的文件捕获。

**参数**

| 参数      | 类型        | 描述                                |
| --------- | ----------- | ----------------------------------- |
| ``pause`` | ``Integer`` | 如果是`1`，则会启用不断增长的文件。 |

**返回**
如果成功则返回**0**。

----
## Project.save()
``app.project.save()``

**描述**
以当前路径保存项目。

**参数**
无.

**返回**
如果成功则返回**0**。

----
## Project.saveAs()
``app.project.saveAs(path)``

**描述**
将当前项目导出到新的唯一文件路径，从新位置打开项目，并关闭以前打开的（和相同的）项目。

**参数**

| 参数     | 类型       | 描述           |
| -------- | ---------- | -------------- |
| ``path`` | ``String`` | 新文件的路径。 |

**返回**
如果成功，则返回**0**，否则返回错误代码。

----
## Project.setEnableTranscodeOnIngest()
``app.project.setEnableTranscodeOnIngest(state);``

**描述**
控制给定项目的接收行为时代码转换的启用。

**参数**

| 参数      | 类型        | 描述       |
| --------- | ----------- | ---------- |
| ``state`` | ``Boolean`` | 所需状态。 |

**返回**
如果成功，则返回**true**。

----
## Project.setGraphicsWhiteLuminance()
``app.project.setGraphicsWhiteLuminance(value)``

**描述**
设置此项目的当前图形白色亮度值。 

**参数**

| 参数      | 类型        | 描述                                                                        |
| --------- | ----------- | --------------------------------------------------------------------------- |
| ``value`` | ``Integer`` | 要使用的值；必须是由提供的值 `project.getSupportedGraphicsWhiteLuminances`. |

**返回**
Returns true if successful.

----
## Project.setProjectPanelMetadata()
``app.project.setProjectPanelMetadata(layout)``

**描述**
Returns the current layout of the Project panel.

**参数**

| 参数       | 类型       | 描述                                                                                                                                 |
| ---------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| ``layout`` | ``String`` | 表示所需的项目面板布局。注意：生成有效布局字符串的唯一已知方法是根据需要设置Project面板，然后使用 `project.getProjectPanelMetadata`. |

**返回**
Returns  **0** if unsuccessful.

----
## Project.setScratchDiskPath()
``app.project.setScratchDiskPath(newPath, whichScratchDiskPath)``

**描述**
将指定的临时磁盘路径更改为新路径。
**参数**

| 参数                | 类型       | 描述                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``newPath``         | ``String`` | 一条新的道路。                                                                                                                                                                                                                                                                                                                                                              |
| ``scratchDiskType`` | ``Enum``   | 枚举值必须是以下值之一： <br>- ``ScratchDiskType.FirstVideoCaptureFolder``<br>- ``ScratchDiskType.FirstAudioCaptureFolder``<br>- ``ScratchDiskType.FirstVideoPreviewFolder``<br>- ``ScratchDiskType.FirstAudioPreviewFolder``<br>- ``ScratchDiskType.FirstAutoSaveFolder``<br>- ``ScratchDiskType.FirstCCLibrariesFolder``<br>- ``ScratchDiskType.FirstCapsuleMediaFolder`` |

- ``ScratchDiskType.FirstAudioCaptureFolder``
- ``ScratchDiskType.FirstVideoPreviewFolder``
- ``ScratchDiskType.FirstAudioPreviewFolder``
- ``ScratchDiskType.FirstAutoSaveFolder``
- ``ScratchDiskType.FirstCCLibrariesFolder``
- ``ScratchDiskType.FirstCapsuleMediaFolder``

**返回**
如果失败，则返回**0**。
