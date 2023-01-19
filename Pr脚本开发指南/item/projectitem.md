# ProjectItem object
``app.project.rootItem.children[index]``

**描述**
项目中的每一项都是一个**projectItem**，包括项目根。

----

# Attributes 属性

----
## ProjectItem.children
``app.project.rootItem.children[index].children``

**描述**
包含在指定项目项中的项目项数组。

**类型**
`projectItemCollection`, 只读.

----
## ProjectItem.getAudioChannelMapping
``app.project.rootItem.children[index].getAudioChannelMapping``

**描述**
当前应用于此**项目项**的音频频道映射。

**类型**
An audioChannelMapping object.

----
## ProjectItem.getOverrideColorSpaceList
``app.project.rootItem.children[index].getOverrideColorSpaceList``

**描述**
*Add a description*
返回包含类似数据的对象

    {
        value: [
            sRGB,
            BT.601 (NTSC),
            BT.601 (PAL),
            BT.709,
            BT.709 (Scene),
            BT.2020,
            BT.2020 (Scene),
            BT.2100 PQ,
            BT.2100 PQ (Scene),
            BT.2100 HLG,
            BT.2100 HLG (Scene),
            DCDM XYZ,
        ]
    };

**类型**
Javascript Object.

----
## ProjectItem.name-
``app.project.rootItem.children[index].name``

**描述**
项目项的名称。

**类型**
String; 读/写.

**示例**
重命名第一个项目项。

    var item = app.project.rootItem.children[0];
    if (item) {
        item.name = item.name + ', updated by PProPanel.';
    } else {
        alert('无法重命名项目项');
    }

----
## ProjectItem.nodeId
``app.project.rootItem.children[index].nodeId``

**描述**
在项目项添加到项目中时，为其分配的唯一ID。
**NOTE**: 区分对同一源媒体的引用。

**类型**
String; 只读.

----
## ProjectItem.teamProjectsAssetId
``app.project.rootItem.children[index].teamProjectsAssetId``

**描述**
项目项的团队项目资产ID。

**类型**
String; 只读.

----
## ProjectItem.treePath
``app.project.rootItem.children[index].treePath``

**描述**
项目项的当前项目位置。例子：

    **\\ProjectName.prproj\\Media\\MXF\\filename.mxf**

**类型**
String; 只读.

----
## ProjectItem.type
``app.project.rootItem.children[index].type``

**描述**
将 **CLIP**, **BIN**, **ROOT**, or **FILE**.

**类型**
Enumerated value; 只读.

----

# Methods 方法

----
## ProjectItem.attachProxy()
``app.project.rootItem.children[index].attachProxy(mediaPath, isHiRes)``

**描述**
将位于``newMediaPath``的媒体作为高分辨率或代理媒体附加到项目项。

**参数**

| 参数          | 类型        | 描述                                               |
| ------------- | ----------- | -------------------------------------------------- |
| ``mediaPath`` | ``String``  | 新分配介质的路径。                                 |
| ``isHiRes``   | ``Integer`` | 新媒体是否应作为代理``0``或高分辨率``1``媒体附加。 |

**返回**
如果成功则返回**0**。

----
## ProjectItem.canChangeMediaPath()
``app.project.rootItem.children[index].canChangeMediaPath()``

**描述**
如果Premiere Pro可以更改与此项目项关联的路径，则返回**true**；否则，返回**false**。

**参数**
无.

**返回**
Boolean; 如果可以更换介质，则为**true**，如果不能更换，则为**false**。

----
## ProjectItem.canProxy()
``app.project.rootItem.children[index].canProxy()``

**描述**
指示是否可以将代理附加到此项目项。

**参数**
无.

**返回**
如果项目项允许附加代理，则返回 **true**; 否则返回 **false**.

----
## ProjectItem.changeMediaPath()
``app.project.rootItem.children[index].changeMediaPath(newPath)``

**描述**
更新项目项以指向新的媒体路径。

**参数**

| 参数               | 类型        | 描述               |
| ------------------ | ----------- | ------------------ |
| ``newPath``        | ``String``  | 媒体文件的新路径。 |
| ``overrideChecks`` | ``Boolean`` | 忽略任何安全问题。 |

**返回**
如果替换成功，则返回**0**。

----
## ProjectItem.clearOutPoint()
``app.project.rootItem.children[index].clearOutPoint()``

**描述**
清除任何指定的输出点；项目项将在``startTime``开始。

**参数**
None

**返回**
如果成功，则返回``0``。

----
## ProjectItem.createBin()
``app.project.rootItem.children[index].createBin(name)``

**描述**
在项目项内创建一个空容器。仅适用于垃圾箱。

**参数**

| 参数     | 类型       | 描述                 |
| -------- | ---------- | -------------------- |
| ``name`` | ``String`` | 新仓位的名称。 |

**返回**
如果成功，则返回表示新bin的项目项；如果失败，则返回**0**。

----
## ProjectItem.createSmartBin()
``app.project.rootItem.children[index].createSmartBin(name, queryString)``

**描述**
创建搜索箱；仅适用于bin项目项。

**参数**

| 参数            | 类型       | 描述                     |
| --------------- | ---------- | ------------------------ |
| ``name``        | ``String`` | 新仓位的名称。     |
| ``queryString`` | ``String`` | 用于搜索的查询字符串。 |

**返回**
如果智能bin创建成功，则返回**0**。

----
## ProjectItem.createSubClip()
``app.project.rootItem.children[index].createSubClip(name, startTime, endTime, hasHardBoundaries, takeAudio, takeVideo)``

**描述**
为现有项目项的子剪辑创建新项目项。

**参数**

| 参数                  | 类型        | 描述                                             |
| --------------------- | ----------- | ------------------------------------------------ |
| ``name``              | ``String``  | 新子ip的名称。                         |
| ``startTime``         | ``String``  | 子剪辑的开始时间，单位为**Ticks**。             |
| ``endTime``           | ``String``  | 子剪辑的结束时间，单位为**Ticks**。               |
| ``hasHardBoundaries`` | ``Integer`` | 如果为``1``，则用户不能扩展``in``和``out``。 |
| ``takeVideo``         | ``Integer`` | 如果``1``，请使用源视频。                 |
| ``takeAudio``         | ``Integer`` | 如果``1``，则使用源音频。                 |

**返回**
返回表示新子ip的项目项，如果创建失败，则返回0。

----
## ProjectItem.deleteBin()
``app.project.rootItem.children[index].deleteBin()``

**描述**
从项目中删除一个 bin，**及其所有内容**。

**参数**
无.

**返回**
如果删除成功返回**0**。

----
## ProjectItem.findItemsMatchingMediaPath()
``app.project.rootItem.children[index].findItemsMatchingMediaPath(pathToMatch, ignoreSubClips)``

**描述**
返回一个项目项数组，所有项目项都引用相同的媒体路径。

**参数**

| 参数               | 类型        | 描述                                    |
| ------------------ | ----------- | --------------------------------------- |
| ``pathToMatch``    | ``String``  | 要匹配的路径。                        |
| ``ignoreSubClips`` | ``Integer`` | 如果为``1``，则不会返回任何子片段。 |

**返回**
返回一个项目项数组，如果找不到与``matchPath``匹配的项目项，则返回 **0**。

----
## ProjectItem.getColorLabel()
``app.project.rootItem.children[index].getColorLabel()``

**描述**
检索项目项的颜色标签。

**参数**
无.

**返回**

``Number``, 之一
| key       |value              |
| ---------- | --------------- |
| labelColor | - 0 = Violet    |
|            | - 1 = Iris      |
|            | - 2 = Caribbean |
|            | - 3 = Lavender  |
|            | - 4 = Cerulean  |
|            | - 5 = Forest    |
|            | - 6 = Rose      |
|            | - 7 = Mango     |
|            | - 8 = Purple    |
|            | - 9 = Blue      |
|            | - 10 = Teal     |
|            | - 11 = Magenta  |
|            | - 12 = Tan      |
|            | - 13 = Green    |
|            | - 14 = Brown    |
|            | - 15= Yellow    |


----
## ProjectItem.getColorSpace()
``app.project.rootItem.children[index].getColorSpace()``

**描述**
检索项目项的颜色空间属性。

**参数**
无.

**返回**
返回项的颜色空间属性。

| 项目 | 名字                      |
| ---- | ------------------------- |
|      | - transfer characteristic |
|      | - primaries.              |
|      | - matrix equation.        |


**代码示例**
这将把上述信息写入事件面板。

    {
    var colorSpace = app.project.rootItem.children[0].getColorSpace()
    app.setSDKEventMessage("Color Space " + " = " + colorSpace.name, 'info');
    app.setSDKEventMessage("Transfer Characteristic " + " = " + colorSpace.transferCharacteristic, 'info');
    app.setSDKEventMessage("Color Primaries " + " = " + colorSpace.primaries, 'info');
    app.setSDKEventMessage("Matrix Equation " + " = " + colorSpace.matrixEquation, 'info');
    }

----
## ProjectItem.getOriginalColorSpace()
``app.project.rootItem.children[index].getOriginalColorSpace()``

**描述**
检索项目项的颜色空间属性。

**参数**
无.

**返回**
如果属性已被覆盖，则返回项的颜色空间属性。
| key   | value                              |
| ----- | ---------------------------------- |
| item. | - original name.                   |
|       | - original transfer characteristic |
|       | - original primaries.              |
|       | - original matrix equation.        |


**代码示例**
See ProjectItem.getColorSpace()

----
## ProjectItem.getEmbeddedLUTID()
``app.project.rootItem.children[index].getEmbeddedLUTID()``

**描述**
检索项目项的 LUTID。

**参数**
无.

**返回**
返回项目的 LUTID

**代码示例**
将LUTID写入事件面板。

    {
    var lutID = app.project.rootItem.children[0].getEmbeddedLUTID()
    app.setSDKEventMessage("LutID " + " = " + lutID, 'info');
    }

----
## ProjectItem.getInputLUTID()
``app.project.rootItem.children[index].getInputLUTID()``

**描述**
检索项目项的输入LUTID。

**参数**
无.

**返回**
返回项目的输入LUTID

**代码示例**
将输入LUTID写入事件面板。

    {
    var lutID = app.project.rootItem.children[0].getInputLUTID()

    app.setSDKEventMessage("Input LutID " + " = " + inputLutID, 'info');
    }

----
## ProjectItem.getFootageInterpretation()
``app.project.rootItem.children[index].getFootageInterpretation()``

**描述**
返回描述projectItem当前解释的结构。

**参数**
无.

**返回**
镜头解释结构，如果不成功，则为“0”。
| key                         | value                                                                                                                                                      |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``alphaUsage``              | 阿尔法，将是以下之一:<br>- 0 ALPHACHANNEL_NONE<br>- 1 ALPHACHANNEL_STRAIGHT<br>- 2 ALPHACHANNEL_PREMULTIPLIED<br>- 3 ALPHACHANNEL_IGNORE    |
| ``fieldType``               | 字段类型，以下之一:  <br>- -1 FIELDTYPE_DEFAULT<br>- 0 FIELDTYPE_PROGRESSIVE<br>- 1 FIELDTYPE_UPPERFIRST<br>- 2 FIELDTYPE_LOWERFIRST         |
| ``ignoreAlpha``             | ``true`` or ``false``.                                                                                                                                     |
| ``invertAlpha``             | ``true`` or ``false``.                                                                                                                                     |
| ``frameRate``               | 帧速率作为浮点值。                                                                                                                     |
| ``pixelAspectRatio``        | 像素纵横比作为浮点值。                                                                                                                |
| ``removePulldown``          | ``true`` or ``false``.                                                                                                                                     |
| ``vrConformProjectionType`` | 用于VR镜头的投影类型。其中之一:<br>- 0 VR_CONFORM_PROJECTION_NONE <br>- 1 VR_CONFORM_PROJECTION_EQUIRECTANGULAR                  |
| ``vrLayoutType``            | VR使用的镜头布局。其中之一： <br>- 0 VR_LAYOUT_MONOSCOPIC  <br>- 1 VR_LAYOUT_STEREO_OVER_UNDER<br>- 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE |
| ``vrHorizontalView``        | 用于VR镜头的水平视图。                                                                                                                |
| ``vrVerticalView``          | 用于VR镜头的垂直视图。                                                                                                                  |

----
## ProjectItem.getInPoint()
``app.project.rootItem.children[index].getInPoint()``

**描述**
获取当前项目项的切入点。

**参数**
无.

**返回**
A `time`, 包含输入点。

----
## ProjectItem.getMarkers()
``app.project.rootItem.children[index].getMarkers()``

**描述**
检索与此项目项关联的``markrCollection``。

**参数**
无.

**返回**
`markerCollection`, 只读;

----
## ProjectItem.getMediaPath()
``app.project.rootItem.children[index].getMediaPath()``

**描述**
以字符串形式返回与项目项的媒体关联的路径。 
**NOTE**: 这只适用于原子介质；此呼叫无法为没有实际路径的媒体提供有意义的路径（这将是合成进口商生成的任何媒体的情况，如Premiere Pro自己的通用计数领导者）。此外，对于图像序列，仅返回序列中第一个图像的路径。

**参数**
无.

**返回**
包含与项目项关联的媒体路径的字符串。

----
## ProjectItem.getOutPoint()
``app.project.rootItem.children[index].getOutPoint(mediaType)``

**描述**
检索指定媒体类型的当前输出点。

**参数**

| 参数          | 类型        | 描述                                                                                                                          |
| ------------- | ----------- |
| ``mediaType`` | ``Integer`` | 仅针对视频传递``1``，或仅针对音频传递``2``。 如果未传递 ``mediaType``，则函数获取所有媒体的出点。 |

**返回**
Returns a `time`.

----
## ProjectItem.getProjectMetadata()
``app.project.rootItem.children[index].getProjectMetadata()``

**描述**
检索与项目项关联的元数据。与媒体XMP不同。

**参数**
无.

**返回**
包含所有Premiere Pro私有项目元数据的字符串，已序列化。

----
## ProjectItem.getProjectColumnsMetadata()
``app.project.rootItem.children[index].getProjectColumnsMetadata()``

**描述**
向用户返回一个JSON字符串，其中包含当前项目视图布局中的所有元数据

**参数**
无.

**返回**
可以在Javascript层中使用JSON.parse（）方法解析的JSON字符串。这将生成一个对象列表，每个对象表示一列。每个对象将包含4个键/值对：ColumnName、ColumnValue、ColumnID和ColumnPath。
ColumnName和ColumnValue用作信息键/值。
ColumnID和ColumnPath可用于通过方法setProjectMetadata（）或setXMPMetadata（）修改该列。

例如：
| Object          | Value                                                       | 描述                     |
| --------------- | ----------------------------------------------------------- | ------------------------ |
| ``ColumnName``  | ``Name``                                                    | 列的名称       |
| ``ColumnValue`` | ``A014C003_180620_R205.mov``                                | 列值示例 |
| ``ColumnID``    | ``Column.Intrinsic.Name``                                   | 列的ID        |
| ``ColumnPath``  | ``http://ns.adobe.com/premierePrivateProjectMetaData/1.0/`` | 列的路径       |


----
## ProjectItem.getProxyPath()
``app.project.rootItem.children[index].getProxyPath()``

**描述**
检索与此项目项关联的代理媒体的路径。

**参数**
无.

**返回**
返回与代理项关联的代理媒体的路径（作为**String**），如果未找到，则返回**0**。

----
## ProjectItem.getXMPMetadata()
``app.project.rootItem.children[index].getXMPMetadata()``

**描述**
以字符串的形式检索与项目项关联的XMP元数据。

**参数**
无.

**返回**
包含所有XMP元数据的字符串，已序列化。

----
## ProjectItem.hasProxy()
``app.project.rootItem.children[index].hasProxy()``

**描述**
指示是否已将代理附加到项目项。

**参数**
无.

**返回**
如果项目项附加了代理，则返回**true****否则为假**。

----
## ProjectItem.isMergedClip()
``app.project.rootItem.children[index].isMergedClip()``

**描述**
指示项目项是否引用合并剪辑。

**参数**
无.

**返回**
如果项目项是合并剪辑，则返回``true``；如果不是，则返回``false``。 

----
## ProjectItem.isMulticamClip()
``app.project.rootItem.children[index].isMulticamClip()``

**描述**
指示项目项是否引用多播剪辑。

**参数**
无.

**返回**
如果项目项是多播剪辑，则返回``true``；如果不是，则返回``false``。

----
## ProjectItem.isOffline()
``app.project.rootItem.children[index].isOffline()``

**描述**
返回指示项目项是否脱机的布尔值。

**参数**
无.

**返回**
Boolean, ``true`` if offline.

----
## ProjectItem.isSequence()
``app.project.rootItem.children[index].isSequence()``

**描述**
指示项目项是否引用``序列``。

**参数**
无.

**返回**
如果项目项是``序列``、多播剪辑或合并剪辑，则返回``true``。如果不是其中任何一个，则返回``false``。

----
## ProjectItem.moveBin()
``app.project.rootItem.children[index].moveBin(newParentBinProjectItem)``

**描述**
将projectItem移动到新的父bin中。

**参数**
无.

**返回**
如果移动成功，则返回**0**。

----
## ProjectItem.refreshMedia()
``app.project.rootItem.children[index].refreshMedia()``

**描述**
强制Premiere Pro更新其与项目项相关的媒体表示。如果媒体以前处于离线状态，这可能会导致其变为在线状态（如果以前丢失的媒体可用）。

**参数**
无.

**返回**
与项目项关联的标记数组，如果没有标记，则为**0**。

----
## ProjectItem.renameBin()
``app.project.rootItem.children[index].renameBin(newName)``

**描述**
更改bin的名称。仅适用于属于箱的项目项。

**参数**

| 参数        | 类型       | 描述            |
| ----------- | ---------- | --------------- |
| ``newName`` | ``String`` | 新的bin名称。 |

**返回**
如果重命名bin成功，则返回**0**。

----
## ProjectItem.select()
``app.project.rootItem.children[index].select()``

**描述**
将项目项（必须是bin）设置为后续导入项目的目标。

**参数**
无.

**返回**
如果项目项已成功成为目标，则返回**0**，以便后续导入。

----
## ProjectItem.setColorLabel()
``app.project.rootItem.children[index].setColorLabel(labelColor)``

**描述**
设置项目项的颜色标签。

**参数**

| 参数           | 类型        | 描述                                            |
| -------------- | ----------- | ----------------------------------------------- |
| ``labelColor`` | ``Integer`` | A label color; see `projectItem.getColorLabel`. |

**返回**
0 if successful.

----
## ProjectItem.setFootageInterpretation()
``app.project.rootItem.children[index].setFootageInterpretation(interpretation)``

**描述**
返回描述projectItem当前解释的结构。

**参数**

| 参数               | 类型 | 描述                                |
| ------------------ | ---- | ----------------------------------- |
| ``interpretation`` |      | A footage interpretation structure. |

**返回**
``true`` if successful.

----
## ProjectItem.setInPoint()
``app.project.rootItem.children[index].setInPoint(time, mediaType)``

**描述**
对于指定的媒体类型，将入点设置为``timeInTicks``。 

**参数**

| 参数          | 类型        | 描述                                                                                                                   |
| ------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------- |
| ``time``      | ``String``  | A time in **Ticks**.                                                                                                   |
| ``mediaType`` | ``Integer`` | 确定要影响的媒体类型；传递``11``仅用于视频，传递``2``仅用于音频，传递“4”用于所有媒体类型。 |

**返回**
如果成功，则返回``0``。

----
## ProjectItem.setOffline()
``app.project.rootItem.children[index].setOffline()``

**描述**
使项目项脱机。

**参数**
无.

**返回**
如果成功，则返回``true``。

----
## ProjectItem.setOutPoint()
``app.project.rootItem.children[index].setOutPoint(time, mediaType)``

**描述**
对于指定的媒体类型，将输出点设置为``timeInTicks``。 

**参数**

| 参数          | 类型        | 描述                                                                                                                   |
| ------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------- |
| ``time``      | ``String``  | A time in **Ticks**.                                                                                                   |
| ``mediaType`` | ``Integer`` | 确定要影响的媒体类型；传递``1``仅用于视频，传递``2``仅用于音频，传递``4``用于所有媒体类型。 |

**返回**
如果成功，则返回``0``。

----
## ProjectItem.setOverrideFrameRate()
``app.project.rootItem.children[index].setOverrideFrameRate(newFrameRate)``

**描述**
设置项目项的帧速率。

**参数**

| 参数             | 类型      | 描述                |
| ---------------- | --------- | ------------------- |
| ``newFrameRate`` | ``Float`` | 新的帧速率。 |

**返回**
如果帧速率已成功更改，则返回**0**。

----
## ProjectItem.setOverridePixelAspectRatio()
``app.project.rootItem.children[index].setOverridePixelAspectRatio(numerator, denominator)``

**描述**
设置项目项的像素纵横比。

**参数**

| 参数            | 类型        | 描述               |
| --------------- | ----------- | ------------------ |
| ``numerator``   | ``Integer`` | 一个新的分子。   |
| ``denominator`` | ``Integer`` | 一个新的分母。 |

**返回**
如果纵横比已成功更改，则返回**0**。

----
## ProjectItem.setProjectMetadata()
``app.project.rootItem.children[index].setProjectMetadata(newMetadata, updatedFields)``

**描述**
设置与项目项关联的私有项目元数据。

**参数**

| 参数              | 类型       | 描述                                                       |
| ----------------- | ---------- | ---------------------------------------------------------- |
| ``newMetadata``   | ``String`` | 新的序列化私有项目元数据。                |
| ``updatedFields`` | ``Array``  | 包含要更新的字段名称的数组。 |

**返回**
Returns 0 if update was successful.

----
## ProjectItem.setScaleToFrameSize()
``app.project.rootItem.children[index].setScaleToFrameSize()``

**描述**
当将此项目项中的媒体插入序列时，打开缩放到帧大小。

**参数**
无.

**返回**
未定义的返回值。

----
## ProjectItem.setStartTime()
``app.project.rootItem.children[index].setStartTime(time)``

**描述**
为项目项分配新的开始时间

**参数**

| 参数     | 类型       | 描述                                           |
| -------- | ---------- | ---------------------------------------------- |
| ``time`` | ``String`` | 新的开始时间，表示为 **Ticks**. |

**返回**
如果成功，则返回``0``。

----
## ProjectItem.setXMPMetadata()
``app.project.rootItem.children[index].setXMPMetadata(newXMP)``

**描述**
设置与项目项关联的XMP元数据。

**参数**

| 参数       | 类型       | 描述                            |
| ---------- | ---------- | ------------------------------- |
| ``newXMP`` | ``String`` | 一个新的序列化XMP元数据。 |

**返回**
如果更新成功，则返回0。

----
## ProjectItem.startTime()
``app.project.rootItem.children[index].startTime()``

**描述**
返回``时间``，表示开始时间。

**参数**
无.

**返回**
`time`.

----
## ProjectItem.videoComponents()
``app.project.rootItem.children[index].videoComponents()``

**描述**
此项目项的``主剪辑``的视频组件。

**类型**
`componentCollection`, 只读.
