# SourceMonitor object
``app.sourceMonitor``

**描述**
Source对象表示Premiere Pro的Source监视器。

----

# Attributes 属性

无.

----

# Methods 方法

----
## SourceMonitor.closeAllClips()
``app.sourceMonitor.closeAllClips()``

**描述**
关闭源监视器中的所有剪辑。

**参数**
无.

**返回**
如果成功则返回**0**。

----
## SourceMonitor.closeClip()
``app.sourceMonitor.closeClip()``

**描述**
关闭源监视器中最前面的剪辑。

**参数**
无.

**返回**
如果成功则返回**0**。

----
## SourceMonitor.getPosition()
``app.sourceMonitor.getPosition()``

**描述**
检索源监视器当前时间指示器的位置。

**参数**
无.

**返回**
返回包含源监视器当前时间指示器位置的``time``。

----
## SourceMonitor.openFilePath()
``app.sourceMonitor.openFilePath(path)``

**描述**
在源监视器中打开文件。

**参数**

| 参数     | 类型       | 描述                 |
| -------- | ---------- | -------------------- |
| ``path`` | ``String`` | 要打开的文件的路径。 |

**返回**
如果成功，则返回``true``。

----
## SourceMonitor.openProjectItem()
``app.sourceMonitor.openProjectItem(projectItem)``

**描述**
在源监视器中打开项目项。

**参数**

| 参数            | 类型          | 描述             |
| --------------- | ------------- | ---------------- |
| ``projectItem`` | `projectItem` | 要打开的项目项。 |


**返回**
如果成功，则返回0.

----
## SourceMonitor.play()
``app.sourceMonitor.play(playbackSpeed)``

**描述**
开始以指定的播放速度播放源监视器。

**参数**

| 参数              | 类型      | 描述       |
| ----------------- | --------- | ---------- |
| ``playbackSpeed`` | ``Float`` | 播放速度。 |

**返回**
如果成功，则返回0.
