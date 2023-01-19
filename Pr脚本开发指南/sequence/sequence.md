# Sequence object
``app.project.sequences[index]``

**描述**
**Sequence** 对象表示 Premiere Pro 中的媒体序列（又名“时间轴”）。

----

# Attributes 属性

----
## Sequence.audioDisplayFormat
``app.project.sequences[index].audioDisplayFormat``

**描述**
*Add a description*

**类型**
Number.

----
## Sequence.audioTracks
``app.project.sequences[index].audioTracks``

**描述**
序列中的一组音轨。

**类型**
`trackCollection`, 只读;

----
Sequence.end
``app.project.sequences[index].end``

**描述**
序列结束的时间，单位为Ticks。

**类型**
String; 只读.

----
## Sequence.frameSizeHorizontal
``app.project.sequences[index].frameSizeHorizontal``

**描述**
序列中帧的水平宽度。

**类型**
Integer; 只读.

----
## Sequence.frameSizeVertical
``app.project.sequences[index].frameSizeVertical``

**描述**
帧的垂直高度，从序列开始。

**类型**
Integer; 只读.

----
## Sequence.id
``app.project.sequences[index].id``

**描述**
这是创建时分配给序列的序号。如果这是在给定的Premiere Pro会话期间在项目中创建的第三十三个序列，则该值将为“33”。

**类型**
Integer, 只读.

----
## Sequence.markers
``app.project.sequences[index].markers``

**描述**
与此序列关联的``Marker <marker>``对象。

**类型**
`markerCollection`, 只读;

----
## Sequence.name
``app.project.sequences[index].name``

**描述**
序列的名称。

**类型**
String; 读/写.

----
## Sequence.projectItem
``app.project.sequences[index].projectItem``

**描述**
与此序列关联的``projectItem``。

**类型**
`projectItem`; 只读.

----
## Sequence.sequenceID
``app.project.sequences[index].sequenceID``

**描述**
创建序列时分配给该序列的唯一标识符，格式为 ``xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx``.

**类型**
String; 只读.

----
## Sequence.timebase
``app.project.sequences[index].timebase``

**描述**
序列中每帧的Tick数。

**类型**
String; 只读.

----
## Sequence.videoDisplayFormat
``app.project.sequences[index].videoDisplayFormat``

**描述**
*Add a description*

**类型**
Number.

----
## Sequence.videoTracks
``app.project.sequences[index].videoTracks``

**描述**
序列中的视频轨道阵列。

**类型**
`trackCollection`, 只读;

----
## Sequence.zeroPoint
``app.project.sequences[index].zeroPoint``

**描述**
序列的开始时间，单位为Ticks。

**类型**
String; 只读.

----

# Methods 方法

----
## Sequence.autoReframeSequence()
``app.project.sequences[index].autoReframeSequence(numerator, denominator, motionPreset, newName, useNestedSequences)``

**描述**
生成新的自动重新命名序列。

**参数**

| 参数                   | 类型        | 描述                                               |
| ---------------------- | ----------- | -------------------------------------------------- |
| ``numerator``          | ``Integer`` | 所需框架纵横比的分子.           |
| ``denominator``        | ``Integer`` | 所需帧纵横比的分母.         |
| ``motionPreset``       | ``String``  | 什么之中的一个:<br>- "slower"<br>- "default"<br>- "faster" |
| ``newName``            | ``String``  | 新创建序列的名称.               |
| ``useNestedSequences`` | ``Boolean`` | 是否接受嵌套序列.                  |

**返回**
如果成功，则返回新的``序列``； `0` 如果不成功。

**示例**

    var sequence = app.project.activeSequence;
    if (sequence) {
        var numerator = 1;
        var denominator = 1;
        var motionPreset = 'default'; // 'default', 'faster', 'slower'
        var newName = sequence.name + ', auto-reframed.';
        var useNestedSequences  = false;

        var newSequence = sequence.autoReframeSequence(numerator, denominator, motionPreset, newName, useNestedSequences);

        if (newSequence) {
            alert('已创建重新框架序列: ' + newName + '.');
        } else {
            alert('无法创建重新构建框架的序列: ' + newName + '.');
        }
    } else {
        alert('无活动序列');
    }

----
## Sequence.createCaptionTrack()
``app.project.activeSequence.createCaptionTrack(projectItem,startAtTime, captionFormat)``

**描述**
使用项目项中的字幕数据在活动序列中创建字幕轨道。

**参数**

| 参数              | 类型                   | 描述                                                                                |
| ----------------- | ---------------------- | ----------------------------------------------------------------------------------- |
| ``projectItem``   | ``ProjectItem object`` | 字幕源剪辑（例如.srt）                                                 |
| ``startAtTime``   | ``Float``              | 从序列开始的偏移量（秒）                                           |
| ``captionFormat`` | ``Constant``           | （可选，默认为副标题）新曲目的标题格式（见下表）。 |

| 标题格式    | 参数                        |
| ------------------ | -------------------------------- |
| Subtitle (Default) | Sequence.CAPTION_FORMAT_SUBTITLE |
| CEA-608            | Sequence.CAPTION_FORMAT_608      |
| CEA-708            | Sequence.CAPTION_FORMAT_708      |
| Teletext           | Sequence.CAPTION_FORMAT_TELETEXT |
| EBU Subtitle       | Sequence.CAPTION_FORMAT_OPEN_EBU |
| OP-42              | Sequence.CAPTION_FORMAT_OP42     |
| OP-47              | Sequence.CAPTION_FORMAT_OP47     |

**返回**
布尔值，如果成功则为true。

**示例**

	var result = app.project.activeSequence.createCaptionTrack(projectItem, 0, Sequence.CAPTION_FORMAT_708);

----
## Sequence.clone()
``app.project.sequences[index].clone()``

**描述**
创建给定序列的克隆。

**参数**
无.

**返回**
返回指示克隆是否成功的布尔值。

----
Sequence.createSubsequence()
``app.project.sequences[index].createSubsequence(ignoreTrackTargeting)``

**描述**
创建新序列，该序列是现有序列的子序列。

**参数**

| 参数                     | 类型        | 描述                                                                                  |
| ------------------------ | ----------- | ------------------------------------------------------------------------------------- |
| ``ignoreTrackTargeting`` | ``Boolean`` | 新序列是否应忽略原始序列中的轨迹目标. |

**返回**
返回新创建的序列，如果不成功，则返回0。

----
## Sequence.exportAsFinalCutProXML()
``app.project.sequences[index].exportAsFinalCutProXML(outputPath)``

**描述**
创建序列及其组成媒体的新FCP XML表示。

**参数**

| 参数           | 类型       | 描述                                      |
| -------------- | ---------- | ----------------------------------------- |
| ``outputPath`` | ``String`` | 新FCP XML文件的输出路径。 |

**返回**
如果成功，则返回0.

----
## Sequence.exportAsMediaDirect()
``app.project.sequences[index].exportAsMediaDirect(outputPath, presetPath, workAreaType)``

**描述**
使用指定的输出预设（.epr文件）并遵循指定的工作区类型，将序列渲染到指定的输出路径。

**参数**

| 参数             | 类型       | 描述                                                                                                           |
| ---------------- | ---------- | -------------------------------------------------------------------------------------------------------------- |
| ``outputPath``   | ``String`` | 渲染媒体的输出路径。                                                                  |
| ``presetPath``   | ``String`` | ???                                                                                                            |
| ``workAreaType`` |            | 必须是以下之一:<br>- 0 ``ENCODE_ENTIRE``<br>- 1 ``ENCODE_IN_TO_OUT``<br>- 2 ``ENCODE_WORK_AREA`` |

**返回**
如果成功，则返回0.

----
## Sequence.exportAsProject()
``app.project.sequences[index].exportAsProject(outputPath)``

**描述**
创建仅包含给定序列及其组成媒体的新``项目``。

**参数**

| 参数           | 类型       | 描述                                 |
| -------------- | ---------- | ------------------------------------ |
| ``outputPath`` | ``String`` | 新项目的输出路径。 |

**返回**
如果成功，则返回0.

----
## Sequence.getExportFileExtension()
``app.project.sequences[index].getExportFileExtension(outputPresetPath)``

**描述**
检索与当前序列关联的文件扩展名。

**参数**

| 参数                 | 类型       | 描述                          |
| -------------------- | ---------- | ----------------------------- |
| ``outputPresetPath`` | ``String`` | 要使用的输出预设. |

**返回**
返回包含输出文件扩展名的 **String**，如果不成功则返回 **0**。

----
## Sequence.getInPoint()
``app.project.sequences[index].getInPoint()``

**描述**
以秒为单位检索当前序列。

**参数**
无.

**返回**
返回表示输入点的实数（以秒为单位）。

----
## Sequence.getInPointAsTime()
``app.project.sequences[index].getInPointAsTime()``

**描述**
检索点中的当前序列。

**参数**
无.

**返回**
返回表示输入点的`时间`，以秒为单位。

----
## Sequence.getOutPoint()
``app.project.sequences[index].getOutPoint()``

**描述**
检索当前序列输出点（以秒为单位）。

**参数**
无.

**返回**
返回表示输出点的实数（以秒为单位）。

----
## Sequence.getOutPointAsTime()
``app.project.sequences[index].getOutPointAsTime()``

**描述**
检索当前序列输出点。

**参数**
无.

**返回**
返回表示输出点的“时间”（以秒为单位）。

----
## Sequence.getPlayerPosition()
``app.project.sequences[index].getPlayerPosition()``

**描述**
检索当前玩家的位置，单位为Ticks。

**参数**
无.

**返回**
返回表示当前玩家位置的`时间`。

----
## Sequence.getSettings()
``app.project.sequences[index].getSettings()``

**描述**
检索当前序列的设置。

**参数**
无.

**返回**
返回序列设置结构。

| key                       | value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``audioChannelCount``     | 序列中的音频通道数。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ``audioChannelType``      | 正在使用的音频通道类型。以下之一:<br>- 0 AUDIOCHANNELTYPE_Mono <br>- 1 AUDIOCHANNELTYPE_Stereo<br>- 2 AUDIOCHANNELTYPE_51<br>- 3 AUDIOCHANNELTYPE_Multichannel<br>- 4 AUDIOCHANNELTYPE_4Channel<br>- 5 AUDIOCHANNELTYPE_8Channel                                                                                                                                                                                                                                                                                                                                                                                                             |
| ``audioDisplayFormat``    | 音频时间码显示格式。以下之一:<br>- 100 TIMEDISPLAY_24Timecode  <br>- 101 TIMEDISPLAY_25Timecode <br>- 102 TIMEDISPLAY_2997DropTimecode <br>- 103 TIMEDISPLAY_2997NonDropTimecode <br>- 104 TIMEDISPLAY_30Timecode <br>- 105 TIMEDISPLAY_50Timecode <br>- 106 TIMEDISPLAY_5994DropTimecode  <br>- 107 TIMEDISPLAY_5994NonDropTimecode<br>- 108 TIMEDISPLAY_60Timecode <br>- 109 TIMEDISPLAY_Frames <br>- 110 TIMEDISPLAY_23976Timecode <br>- 111 TIMEDISPLAY_16mmFeetFrames  <br>- 112 TIMEDISPLAY_35mmFeetFrames  <br>- 113 TIMEDISPLAY_48Timecode <br>- 200 TIMEDISPLAY_AudioSamplesTimecode  <br>- 201 TIMEDISPLAY_AudioMsTimecode |
| ``audioSampleRate``       | 序列中的音频采样率，如``int``。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ``compositeLinearColor``  | 序列是否以线性颜色合成。如果为真，则为1。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ``editingMode``           | 正在使用的编辑模式的GUID。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ``maximumBitDepth``       | 序列是否在最大深度合成；如果为真，则为1。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ``maximumRenderQuality``  | 序列是否以最高质量呈现；如果为真，则为1。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ``previewCodec``          | 正在使用的预览编解码器的四个字符代码。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ``previewFrameWidth``     | 预览帧的宽度。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ``previewFrameHeight``    | 预览帧的高度。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ``previewFileFormat``     | 用于预览文件渲染的输出预设（.epr文件）的路径。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ``videoDisplayFormat``    | 视频时间显示格式。以下之一: <br>- 100 TIMEDISPLAY_24Timecode<br> - 101 TIMEDISPLAY_25Timecode <br> - 102 TIMEDISPLAY_2997DropTimecode <br> - 103 TIMEDISPLAY_2997NonDropTimecode <br> - 104 TIMEDISPLAY_30Timecode <br> - 105 TIMEDISPLAY_50Timecode <br> - 106 TIMEDISPLAY_5994DropTimecode <br> - 107 TIMEDISPLAY_5994NonDropTimecode <br> - 108 TIMEDISPLAY_60Timecode<br> - 109 TIMEDISPLAY_Frames <br> - 110 TIMEDISPLAY_23976Timecode <br> - 111 TIMEDISPLAY_16mmFeetFrames<br>- 112 TIMEDISPLAY_35mmFeetFrames<br>- 113 TIMEDISPLAY_48Timecode<br>- 200 TIMEDISPLAY_AudioSamplesTimecode<br>- 201 TIMEDISPLAY_AudioMsTimecode   |
| ``videoFieldType``        | 按顺序使用的视频字段类型。其中之一:<br>- -1 FIELDTYPE_DEFAULT  <br>- 0 FIELDTYPE_PROGRESSIVE <br>- 1 ALPHACHANNEL_UPPERFIRST<br> - 2 ALPHACHANNEL_LOWERFIRST                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ``videoFrameHeight``      | 序列视频帧的高度。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ``videoFrameWidth``       | 序列视频帧的高度。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ``videoPixelAspectRatio`` | 像素纵横比，作为比率，作为字符串。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ``vrHorzCapturedView``    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ``vrVertCapturedView``    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ``vrLayout``              | VR使用的镜头布局。其中之一: <br>- 0 VR_LAYOUT_MONOSCOPIC  <br>- 1 VR_LAYOUT_STEREO_OVER_UNDER <br>- 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ``vrProjection``          | 用于VR镜头的投影类型。其中之一:<br>- 0 VR_LAYOUT_MONOSCOPIC <br> - 1 VR_LAYOUT_STEREO_OVER_UNDER <br> - 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ``videoFieldType``        | 字段类型按顺序排列。以下之一:<br>- -1 FIELDTYPE_DEFAULT <br>- 0 FIELDTYPE_PROGRESSIVE<br>- 1 ALPHACHANNEL_UPPERFIRST  <br>- 2 ALPHACHANNEL_LOWERFIRST                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

----
## Sequence.isDoneAnalyzingForVideoEffects()
``app.project.sequences[index].isDoneAnalyzingForVideoEffects()``

**描述**
返回序列是否已完成视频效果分析。

**参数**
无.

**返回**
如果分析完成，则返回``true``。

----
## Sequence.importMGT()
| ``app.project.sequences[index].videotracks[index].importMGT``
| ``app.project.sequences[index].audiotracks[index].importMGT``

**描述**
在指定时间将After Effects运动图形模板（Mogt）导入到选定轨迹。 

**参数**

| 参数               | 类型        | 描述                                                                               |
| ------------------ | ----------- | ---------------------------------------------------------------------------------- |
| ``path``           | ``String``  | 在After Effects中创建的有效.mogrt的完整路径                              |
| ``time``           | ``String``  | 插入.mogrt的时间，以记号表示                                           |
| ``vidTrackOffset`` | ``Integer`` | 从第0个视频曲目中插入多少曲目。mogt内容  |
| ``audTrackOffset`` | ``Integer`` | 从第0个音轨中插入.mogrt内容的音轨数。 |

**返回**
A trackItem object.

----
## Sequence.importMGTFromLibrary()
| ``app.project.sequences[index].videotracks[index].importMGTFromLibrary()``
| ``app.project.sequences[index].audiotracks[index].importMGTFromLibrary()``

**描述**
在指定时间从当前PPro用户的Creative Cloud Library中导入一个After Effects运动图形模板（Mogt）到所选轨迹。 

**参数**

| 参数               | 类型        | 描述                                                                               |
| ------------------ | ----------- | ---------------------------------------------------------------------------------- |
| ``libraryName``    | ``String``  | 图书馆名称（来自当前PPro用户的Creative Cloud Library）            |
| ``mgtName``        | ``String``  | 该库中.mogrt的名称                                                 |
| ``time``           | ``String``  | 插入.mogrt的时间，以记号表示                                           |
| ``vidTrackOffset`` | ``Integer`` | 从第0个视频曲目中插入多少曲目。mogt内容  |
| ``audTrackOffset`` | ``Integer`` | 从第0个音轨中插入.mogrt内容的音轨数。 |


**返回**
一个`trackItem`对象。

----
## Sequence.performSceneEditDetectionOnSelection()
``app.project.sequences[index].performSceneEditDetectionOnSelection(actionDesired, applyCutsToLinkedAudio, sensitivity)``

**描述**
对序列选择执行剪切检测。 

**参数**

| 参数                       | 类型        | 描述                                                                          |
| -------------------------- | ----------- | ----------------------------------------------------------------------------- |
| ``actionDesired``          | ``String``  | One of:<br>- "CreateMarkers"<br>- "ApplyCuts"                                 |
| ``applyCutsToLinkedAudio`` | ``Boolean`` |
| ``sensitivity``            | ``String``  | One of:<br>- "LowSensitivity"<br>- "MediumSensitivity"<br>- "HighSensitivity" |

**返回**
如果成功，则返回``true``。

----
## Sequence.setInPoint()
``app.project.sequences[index].setInPoint(time)``

**描述**
指定点中的新序列。

**参数**

| 参数     | 类型       | 描述                     |
| -------- | ---------- | ------------------------ |
| ``time`` | ``String`` | 新的时间 **ticks**. |

**返回**
如果成功则返回**0**。

----
## Sequence.setOutPoint()
``app.project.sequences[index].setOutPoint(time)``

**描述**
Specifies a new sequence out point.

**参数**

| 参数     | 类型       | 描述                     |
| -------- | ---------- | ------------------------ |
| ``time`` | ``String`` | 新的时间 **ticks**. |

**返回**
如果成功则返回**0**。

----
## Sequence.setPlayerPosition()
``app.project.sequences[index].setPlayerPosition(time)``

**描述**
以 Ticks 为字符串指定新的玩家位置。

**参数**

| 参数     | 类型       | 描述                     |
| -------- | ---------- | ------------------------ |
| ``time`` | ``String`` | **ticks** 的新时间。 |

**返回**
如果成功则返回**0**。

----
## Sequence.setSettings()
``app.project.sequences[index].setSettings(sequenceSettings)``

**描述**
设置当前序列的设置。 *[Editorial: I apologize for any perceived pedantry; sometimes, obvious documentation needs to be obvious. -bbb]*

**参数**

| 参数                 | 类型 | 描述                                                                                         |
| -------------------- | ---- | -------------------------------------------------------------------------------------------- |
| ``sequenceSettings`` |      | 序列设置结构，通过``Sequence.getSettings() <sequence.getSettings>``获得。 |


**返回**
如果成功，则返回0.

----
## Sequence.setZeroPoint()
``app.project.sequences[index].setZeroPoint(newZeroPoint)``

**描述**
设置序列的开始时间。

**参数**

| 参数             | 类型       | 描述                             |
| ---------------- | ---------- | -------------------------------- |
| ``newZeroPoint`` | ``String`` | 新的起点 **ticks**. |

**类型**
Integer; 只读.

**返回**
如果成功则返回**0**。
