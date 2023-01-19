# TrackItem object
|   ``app.project.sequences[index].audioTracks[index].clips[index]``
|   ``app.project.sequences[index].videoTracks[index].clips[index]``

**描述**
**trackItem**对象表示``序列``中视频或音频曲目上的项目。

----

# Attributes 属性

----
## TrackItem.components


|   ``app.project.sequences[index].audioTracks[index].clips[index].components``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components``

**描述**
与此trackItem关联的组件。这可以包括内在转换，以及视频和音频效果。

**类型**
`componentCollection`, read-only;

----
## TrackItem.duration
|   ``app.project.sequences[index].audioTracks[index].clips[index].duration``
|   ``app.project.sequences[index].videoTracks[index].clips[index].duration``

**描述**
trackItem的持续时间。

**类型**
`time`, 只读.

----
## TrackItem.end
|   ``app.project.sequences[index].audioTracks[index].clips[index].end``
|   ``app.project.sequences[index].videoTracks[index].clips[index].end``

**描述**
trackItem的结束时间。注意：这可能与trackItem的输出点不同。

**类型**
`time`, 读/写.

----
## TrackItem.inPoint
|   ``app.project.sequences[index].audioTracks[index].clips[index].inPoint``
|   ``app.project.sequences[index].videoTracks[index].clips[index].inPoint``

**描述**
此trackItem中的媒体入口。

**类型**
`time`, 读/写.

----
## TrackItem.matchName
|   ``app.project.sequences[index].audioTracks[index].clips[index].matchName``
|   ``app.project.sequences[index].videoTracks[index].clips[index].matchName``

**描述**
*Add a description*

**类型**
String; 只读.

----
## TrackItem.mediaType
|   ``app.project.sequences[index].audioTracks[index].clips[index].mediaType``
|   ``app.project.sequences[index].videoTracks[index].clips[index].mediaType``

**描述**
此trackItem提供的媒体类型。

**类型**
String, either **Audio** or **Video**.

----
## TrackItem.name-
|   ``app.project.sequences[index].audioTracks[index].clips[index].name``
|   ``app.project.sequences[index].videoTracks[index].clips[index].name``

**描述**
轨道项目的名称。

**类型**
String; 读/写.

----
## TrackItem.nodeId
|   ``app.project.sequences[index].audioTracks[index].clips[index].nodeId``
|   ``app.project.sequences[index].videoTracks[index].clips[index].nodeId``

**描述**
*Add a description*

**类型**
String.

----
## TrackItem.outPoint
|   ``app.project.sequences[index].audioTracks[index].clips[index].outPoint``
|   ``app.project.sequences[index].videoTracks[index].clips[index].outPoint``

**描述**
此trackItem中的媒体输出点.

**类型**
`time`, 读/写.

----
## TrackItem.projectItem
|   ``app.project.sequences[index].audioTracks[index].clips[index].projectItem``
|   ``app.project.sequences[index].videoTracks[index].clips[index].projectItem``

**描述**
从中绘制媒体的“projectItem”。

**类型**
A `projectItem`. 

----
## TrackItem.start
|   ``app.project.sequences[index].audioTracks[index].clips[index].start``
|   ``app.project.sequences[index].videoTracks[index].clips[index].start``

**描述**
trackItem的开始时间。注意：这可能不同于trackItem的切入点。

**类型**
`time`, 读/写.

----
## TrackItem.type
|   ``app.project.sequences[index].audioTracks[index].clips[index].type``
|   ``app.project.sequences[index].videoTracks[index].clips[index].type``

**描述**
此trackItem提供的媒体类型。

**类型**
Number, **1** 表示视频, **2** 表示音频.

----

# Methods 方法

----
## TrackItem.getMGTComponent()
| ``app.project.sequences[index].videotracks[index].getMGTComponent``
| ``app.project.sequences[index].audiotracks[index].getMGTComponent``

**描述**
在指定时间向选定轨迹添加After Effects运动图形模板（Mogt）。 

**参数**

| 参数               | 类型        | 描述                                                                                    |
| ------------------ | ----------- | --------------------------------------------------------------------------------------- |
| ``mogrtPath``      | ``String``  | 在After Effects中创建的有效.mogrt的完整路径                                   |
| ``targetTime``     | ``String``  | 插入.mogrt的时间，以记号表示                                        |
| ``vidTrackOffset`` | ``Integer`` | 从0（第一个可用曲目）开始的偏移量，在该偏移量上插入.mogrt中的视频 |
| ``audTrackOffset`` | ``Integer`` | 从0（第一个可用曲目）开始的偏移量，在该偏移量上插入.mogrt中的音频 |

**返回**
一个Component对象，表示创建者已公开的.mogrt的参数。


----
## TrackItem.getSpeed()
|   ``app.project.sequences[index].audioTracks[index].clips[index].getSpeed()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].getSpeed()``

**描述**
返回应用于``trackItem``的速度乘数。

**参数**
无.

**返回**
返回应用于 ``trackItem`` 的速度乘数，作为 ``float``。 无速度调整 = ``1``。

----
## TrackItem.isAdjustmentLayer()
|   ``app.project.sequences[index].audioTracks[index].clips[index].isAdjustmentLayer()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].isAdjustmentLayer()``

**描述**
返回``trackItem``是否为调整层。

**参数**
无.

**返回**
如果跟踪项是调整层，则返回 true ； ``false`` 如果不是。

----
## TrackItem.isSpeedReversed()mm
|   ``app.project.sequences[index].audioTracks[index].clips[index].isSpeedReversed()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].isSpeedReversed()``

**描述**
返回trackItem是否反转。

**参数**
无.

**返回**
如果 ``trackItem`` 被反转，则返回 **1**； **0** 如果没有。

----
## TrackItem.isSelected()
|   ``app.project.sequences[index].audioTracks[index].clips[index].isSelected()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].isSelected()``

**描述**
检索 trackItem 的当前选择状态。

**参数**
无.

**返回**
如果选择了 trackItem，则返回``true``； ``false`` 如果不是。

----
## TrackItem.setSelected()
|   ``app.project.sequences[index].audioTracks[index].clips[index].setSelected(state, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].setSelected(state, updateUI)``

**描述**
设置trackItem的选择状态。

**参数**

| 参数         | 类型        | 描述                                                                            |
| ------------ | ----------- | ------------------------------------------------------------------------------- |
| ``state``    | ``Integer`` | 如果``1``，则选择曲目项；如果``0``，则将取消选择。     |
| ``updateUI`` | ``Integer`` | 如果``1``，则在进行此函数调用后，Premiere Pro UI将更新。 |

**返回**
如果成功则返回**0**。

----
## TrackItem.getMatchName()
|   ``app.project.sequences[index].audioTracks[index].clips[index].getMatchName()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].getMatchName()``

**描述**
检索trackItem的匹配名称。

**参数**
无.

**返回**
如果成功，将匹配名称返回为**字符串**。

----
## TrackItem.remove()
|   ``app.project.sequences[index].audioTracks[index].clips[index].remove(inRipple, inAlignToVideo)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].remove(inRipple, inAlignToVideo)``

**描述**
设置 trackItem 的选择状态。

**参数**

| 参数               | 类型        | 描述                                                                                                                  |
| ------------------ | ----------- | --------------------------------------------------------------------------------------------------------------------- |
| ``inRipple``       | ``Boolean`` | 如果``1``，则稍后的曲目项将更早移动，以填补空白；如果为``0``，则后续曲目项将保留在原位。 |
| ``inAlignToVideo`` | ``Boolean`` | 如果``1``，Premiere Pro会将移动的曲目项目与最近视频帧的开头对齐。                          |


**返回**
如果成功则返回**0**。

----
## TrackItem.disabled
|   ``app.project.sequences[index].audioTracks[index].clips[index].disabled``
|   ``app.project.sequences[index].videoTracks[index].clips[index].disabled``

**描述**
设置 trackItem 的禁用状态. 读/写.

**参数**
| 参数                | 类型        | 描述                                                                       |
| ------------------- | ----------- | -------------------------------------------------------------------------- |
| ``newDisableState`` | ``Boolean`` | 如果为 true，则该 trackItem 将被禁用； 如果为“false”，trackItem 将被启用。 |

**返回**
如果成功则返回**0**。

----
## TrackItem.move()
|   ``app.project.sequences[index].audioTracks[index].clips[index].move(newInPoint)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].move(newInPoint)``

**描述**
将轨迹项目的inPoint移动到新时间，方法是将其移动几秒。

**参数**
| 参数           | 类型       | 描述                                                 |
| -------------- | ---------- | ---------------------------------------------------- |
| ``newInPoint`` | ``Number`` | 一个时间对象，表示以秒为单位移动轨迹项目开始的时间。 |

**返回**
如果成功则返回**0**。
