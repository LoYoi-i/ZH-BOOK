# Component object
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index]``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index]``

**描述**
**component** 对象表示已添加或应用于 trackItem 的内容。

----

# Attributes 属性

----
## Component.displayName
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].displayName``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].displayName``

**描述**
显示给用户的组件的名称。本地化。

**类型**
String; 只读.

----
## Component.matchName
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].matchName``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].matchName``

**描述**
从磁盘加载组件时的组件名称；用于唯一标识效果插件。

**类型**
String; 只读.

----
## Component.properties
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties``

**描述**
相关部件的特性；通常，这些是效果参数。

**类型**
Array of components, 只读; (ComponentParamCollection 对象).
