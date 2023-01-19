# Encoder object
``app.encoder``

**描述**
**encoder** 对象表示 Adobe Media Encoder，用于 Premiere Pro 之外的本地渲染。

警告：app.encoder 在 Premiere Pro 14.3.1 - 15 only on Mac 上损坏。 固定在 22 及以上。
https://community.adobe.com/t5/premiere-pro-discussions/missing-the-object-app-encoder-14-3-1-15-0-15-1-15-2/m-p/12544488

----
# Attributes 属性

无.

----

# Methods 方法

----
## Encoder.encodeFile()
``app.encoder.encodeFile(filePath, outputPath, presetPath, workArea, removeUponCompletion)``

**描述**
使用指定的设置，使Adobe Media Encoder渲染指定的文件（可选地，在指定的范围内）。

**Parameters**

| 参数                     | 类型        | 描述                                                                                                                 |
| ------------------------ | ----------- | -------------------------------------------------------------------------------------------------------------------- |
| ``filePath``             | ``String``  | 要渲染的文件的路径。                                                                                                 |
| ``outputPath``           | ``String``  | 输出文件的路径。                                                                                                     |
| ``presetPath``           | ``String``  | 预设（.epr）文件的路径。                                                                                             |
| ``workArea``             | ``Integer`` | 整数表示要使用的工作区域：<br> - 0 - ``ENCODE_ENTIRE``  <br>- 1 - ``ENCODE_IN_TO_OUT``<br>- 2 - ``ENCODE_WORK_AREA`` |
| ``removeUponCompletion`` | ``Integer`` | 如果为`1`，则作业完成后将被删除。                                                                                    |
| ``inPoint``              | Time        | 一个时间 **Time**, 用于新文件的切入点。                                                                              |
| ``outPoint``             | Time        | 一个时间 **Time**, 用于新文件的输出点。                                                                              |

**返回**
对于添加到AME队列的渲染作业，返回作业ID，格式为**String**，如果不成功，则返回**0**。

----
## Encoder.encodeProjectItem()
``app.encoder.encodeProjectItem(projectItem, outputPath, presetPath, workArea, removeUponCompletion)``

**描述**
使用指定的设置，使Adobe Media Encoder呈现指定的：ref:`projectItem`（可选地，从指定的范围）。

**Parameters**

| 参数                     | 类型          | 描述                                                                                                                    |
| ------------------------ | ------------- | ----------------------------------------------------------------------------------------------------------------------- |
| ``projectItem``          | `projectItem` | 要渲染的文件的路径。                                                                                                    |
| ``outputPath``           | ``String``    | 输出文件的路径。                                                                                                        |
| ``presetPath``           | ``String``    | 预设（.epr）文件的路径。                                                                                                |
| ``workArea``             | ``Integer``   | 整数表示要使用的工作区域： <br> - 0 - ``ENCODE_ENTIRE`` <br> - 1 - ``ENCODE_IN_TO_OUT`` <br> - 2 - ``ENCODE_WORK_AREA`` |
| ``removeUponCompletion`` | ``Integer``   | 如果为`1`，则作业完成后将被删除。                                                                                       |


**返回**
对于添加到AME队列的渲染作业，返回作业ID，格式为**String**，如果不成功，则返回**0**。

----
## Encoder.encodeSequence()
``app.encoder.encodeSequence(sequence, outputPath, presetPath, workArea, removeUponCompletion)``

**描述**
使用指定的设置使Adobe Media Encoder呈现指定的：`sequence`。

**Parameters**

| 参数                     | 类型        | 描述                                                                                                                   |
| ------------------------ | ----------- | ---------------------------------------------------------------------------------------------------------------------- |
| ``sequence``             | `sequence`  | 要渲染的文件的路径。                                                                                                   |
| ``outputPath``           | ``String``  | 输出文件的路径。                                                                                                       |
| ``presetPath``           | ``String``  | 预设（.epr）文件的路径。                                                                                               |
| ``workArea``             | ``Integer`` | 整数表示要使用的工作区域： <br>- 0 - ``ENCODE_ENTIRE``  <br>- 1 - ``ENCODE_IN_TO_OUT``  <br>- 2 - ``ENCODE_WORK_AREA`` |
| ``removeUponCompletion`` | ``Integer`` | 如果为`1`，则作业完成后将被删除。                                                                                      |


**返回**
对于添加到AME队列的渲染作业，返回作业ID，格式为**String**，如果不成功，则返回**0**。

----
## Encoder.launchEncoder()
``app.encoder.launchEncoder()``

**描述**
启动Adobe Media Encoder。

**Parameters**
无.

**返回**
如果成功则返回**0**。

----
## Encoder.setEmbeddedXMPEnabled()
``app.encoder.setEmbeddedXMPEnabled(enabled)``

**描述**
确定是否输出嵌入的XMP元数据。

**Parameters**

| 参数        | 类型        | 描述                                   |
| ----------- | ----------- | -------------------------------------- |
| ``enabled`` | ``Integer`` | 传递`1`以启用侧车输出，传递`0`以禁用。 |

**返回**
如果成功则返回**0**。

注意：Premiere Pro和Adobe Media Encoder将为某些文件格式输出sidecar XMP，并为大多数文件格式嵌入XMP。应用程序基于多种因素做出这一决定，对于通常使用“其他方法”的格式，没有API控制来“强制”sidecar或嵌入式输出。

----
## Encoder.setSidecarXMPEnabled()
``app.encoder.setSidecarXMPEnabled(enabled)``

**描述**
确定是否输出包含XMP元数据的sidecar文件。

**Parameters**

| 参数                         | 类型                                   | 描述 |
| ---------------------------- | -------------------------------------- | ---- |
| ``enabled``      ``Integer`` | 传递`1`以启用侧车输出，传递`0`以禁用。 |


**返回**
如果成功则返回**0**。

----
## Encoder.startBatch()
``app.encoder.startBatch()``

**描述**
使Adobe Media Encoder开始渲染其渲染队列。

**Parameters**
无.

**返回**
如果成功则返回**0**。
