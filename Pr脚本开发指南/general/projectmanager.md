# ProjectManager object
``app.projectManager.options``

**描述**
ProjectManager对象公开Premiere Pro的Project Manager，用于项目合并、传输和代码转换。

----

# Attributes 属性

----
## ProjectManager.affectedSequences
``app.projectManager.options.affectedSequences``

**描述**
要导出的 `Sequence <sequence>` 对象的 `Array`。

**类型**
Array; 读/写.

----
## ProjectManager.clipTranscoderOption
``app.projectManager.options.clipTranscoderOption``

**描述**
剪辑转码的指定设置。值将为以下值之一：

| key                               | value                                 |
| --------------------------------- | ------------------------------------- |
| ``CLIP_TRANSCODE_MATCH_PRESET``   | 使用指定预设进行转码。 |
| ``CLIP_TRANSCODE_MATCH_CLIPS``    | 匹配剪辑                       |
| ``CLIP_TRANSCODE_MATCH_SEQUENCE`` | 必须是以下之一：         |

**类型**
String; 读/写.

----
## ProjectManager.clipTransferOption
``app.projectManager.options.clipTransferOption``

**描述**
剪辑传输的指定设置。值将为以下值之一：

| key                         | value                               |
| --------------------------- | ----------------------------------- |
| ``CLIP_TRANSFER_COPY``      | 复制整个源媒体。           |
| ``CLIP_TRANSFER_TRANSCODE`` | 转换为默认输出格式。 |

----
## ProjectManager.convertAECompsToClips
``app.projectManager.options.convertAECompsToClips``

**描述**
如果为`true`，则将动态链接的After Effects合成渲染到新媒体（使用指定的输出预设）。

**类型**
Boolean; 读/写.

----
## ProjectManager.convertImageSequencesToClips
``app.projectManager.options.convertImageSequencesToClips``

**描述**
如果为`true`，则将图像序列转码为新媒体（使用指定的输出预设）。

**类型**
Boolean; 读/写.

----
## ProjectManager.convertSyntheticsToClips
``app.projectManager.options.convertSyntheticsToClips``

**描述**
如果为`true`，则将剪辑从合成导入器转码为新媒体（使用指定的输出预设）。

**类型**
Boolean; 读/写.

----
## ProjectManager.copyToPreventAlphaLoss
``app.projectManager.options.copyToPreventAlphaLoss``

**描述**
如果`true`，则将任何可用的alpha信息包括到转码媒体中。

**类型**
Boolean; 读/写.

----
## ProjectManager.destinationPath
``app.projectManager.options.destinationPath``

**描述**
导出项目和媒体的路径。

**类型**
String; 读/写.

----
## ProjectManager.encoderPresetFilePath
``app.projectManager.options.encoderPresetFilePath``

**描述**
要使用的输出预设（.epr文件）的路径。

**类型**
String; 只读.

----
## ProjectManager.excludeUnused
``app.projectManager.options.excludeUnused``

**描述**
如果非零，则从导出的项目中排除未使用的项目项。

**类型**
Boolean; 读/写.

----
## ProjectManager.handleFrameCount
``app.projectManager.options.handleFrameCount``

**描述**
包括多少帧媒体“处理”镜头（在进出点之前和之后）。

**类型**
Integer; 读/写.

----
## ProjectManager.includeAllSequences
``app.projectManager.options.includeAllSequences``

**描述**
如果为`true`，则导出导出项目中的所有`Sequences <sequence>`。

**类型**
Boolean; 读/写.

----
## ProjectManager.includeConformedAudio
``app.projectManager.options.includeConformedAudio``

**描述**
如果为`true`，则在导出的项目中包含符合要求的音频文件。

**类型**
Boolean; 读/写.

----
## ProjectManager.includePreviews
``app.projectManager.options.includePreviews``

**描述**
如果为`true`，则在导出的项目中包含渲染的预览文件。

**类型**
Boolean; 读/写.

----
## ProjectManager.renameMedia
``app.projectManager.options.renameMedia``

**描述**
如果为`true`，则在导出过程中执行重命名。
**类型**
Boolean; 读/写.
