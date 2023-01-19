Track object
|   ``app.project.sequences[index].audioTracks[index]``
|   ``app.project.sequences[index].videoTracks[index]``

**描述**
**Track** 对象表示``序列``中的视频或音频轨道。

----

# Attributes 属性

----
## Track.clips
|   ``app.project.sequences[index].audioTracks[index].clips``
|   ``app.project.sequences[index].videoTracks[index].clips``

**描述**
按时间顺序包含在轨道中的`Track item <trackItem>`对象数组。

**类型**
`trackItemCollection`, read-only;

----
## Track.id-
|   ``app.project.sequences[index].audioTracks[index].id``
|   ``app.project.sequences[index].videoTracks[index].id``

**描述**
这是创建时 分配给轨道的序号。

**类型**
Integer, 只读.

----
## Track.mediaType
|   ``app.project.sequences[index].audioTracks[index].mediaType``
|   ``app.project.sequences[index].videoTracks[index].mediaType``

**描述**

此轨道中包含的媒体类型。

**类型**

String, 只读; 有效值为“音频”和“视频”。

----
## Track.name
|   ``app.project.sequences[index].audioTracks[index].name``
|   ``app.project.sequences[index].videoTracks[index].name``

**描述**
The name of the track.

**类型**
String; 只读.

----
## Track.transitions
|   ``app.project.sequences[index].audioTracks[index].transitions``
|   ``app.project.sequences[index].videoTracks[index].transitions``

**描述**
按时间顺序包含在轨迹中的变换对象数组。

**类型**
`trackItemCollection`, 只读;

----

# Methods 方法

----
## Track.insertClip()
|   ``app.project.sequences[index].audioTracks[index].insertClip(projectItem, time)``
|   ``app.project.sequences[index].videoTracks[index].insertClip(projectItem, time)``

**描述**
在指定时间将“剪辑”（来自``projectItem``的媒体片段）添加到轨道。 届时将插入媒体。

**参数**

| 参数            | 类型          | 描述                                                 |
| --------------- | ------------- | ---------------------------------------------------- |
| ``projectItem`` | `projectItem` | 从中获取媒体的项目项。              |
| ``time``        | ``String``    | 添加项目项的时间，以 **Ticks** 为单位。 |

**返回**
无.

----
## Track.isMuted()
|   ``app.project.sequences[index].audioTracks[index].isMuted()``
|   ``app.project.sequences[index].videoTracks[index].isMuted()``

**描述**
检索轨迹的当前静音状态。

**参数**
无.

**返回**
如果曲目当前静音，则返回 **true**；**false** 如果不是。

----
## Track.overwriteClip()
|   ``app.project.sequences[index].audioTracks[index].overwriteClip(projectItem, time)``
|   ``app.project.sequences[index].videoTracks[index].overwriteClip(projectItem, time)``

**描述**
在指定时间将“剪辑”（来自``projectItem``的媒体片段）添加到轨道。 这将在那时覆盖任何现有媒体。

**参数**

| 参数            | 类型          | 描述                                                 |
| --------------- | ------------- | ---------------------------------------------------- |
| ``projectItem`` | `projectItem` | 从中获取媒体的项目项。              |
| ``time``        | ``String``    | 添加项目项的时间，以 **Ticks** 为单位。 |

**返回**
Returns ``true``.

----
## Track.setMute()
|   ``app.project.sequences[index].audioTracks[index].setMute(isMuted)``
|   ``app.project.sequences[index].videoTracks[index].setMute(isMuted)``

**描述**
设置轨迹的静音状态。

**参数**

| 参数        | 类型        | 描述                                                           |
| ----------- | ----------- | -------------------------------------------------------------- |
| ``isMuted`` | ``Integer`` | 如果``1``，则将曲目静音。如果``0``，曲目将被取消静音。 |

**返回**
如果成功，则返回0.
