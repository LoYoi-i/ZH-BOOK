# Marker object

|   ``app.project.activeSequence.markers.getFirstMarker()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker()``

**描述**

`Project items <projectItem>` 和 `sequences <sequence>` 都有关联的 **marker** 对象，表示它们的关联标记。

----


# Attributes 属性

----
## Marker.comments

   ``app.project.activeSequence.markers.getFirstMarker().comments``
   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().comments``

**描述**
标记中的注释。

**类型**
String; 读/写.

----
## Marker.end
|   ``app.project.activeSequence.markers.getFirstMarker().end``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().end``

**描述**
A `time` 包含标记结束的值。

**类型**
`time`; 读/写.

----
## Marker.guid
|   ``app.project.activeSequence.markers.getFirstMarker().guid``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().guid``

**描述**
在实例化时创建的标记的唯一标识符。

**类型**
String; 只读.

----
## Marker.name-
|   ``app.project.activeSequence.markers.getFirstMarker().name``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().name``

**描述**
标记的名称。

**类型**
String; 读/写.

----
## Marker.start
|   ``app.project.activeSequence.markers.getFirstMarker().start``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().start``

**描述**
A `time` 包含标记开头的值。

**类型**
`time`; 读/写.

----
## Marker.type
|   ``app.project.activeSequence.markers.getFirstMarker().type``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().type``

**描述**
标记的类型; either "Comment", "Chapter", "Segmentation", or "WebLink". Note: Premiere Pro可以导入一些标记类型，这些标记类型无法在Premiere Pro中创建。

**类型**
String; 只读.

----

# Methods 方法

----
## Marker.getColorByIndex()
|   ``app.project.activeSequence.markers.getFirstMarker().getColorByIndex(index)``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().getColorByIndex(index)``

    此功能是在Adobe Premire Pro 13.x中添加的。

**描述**
获取标记颜色索引。

**参数**

| 参数      | 类型        | 描述                            |
| --------- | ----------- | ------------------------------- |
| ``index`` | ``Integer`` | 要读取的标记的索引。 |


**返回**
Returns the color index as an ``Integer``.

----
## Marker.getWebLinkFrameTarget()
|   ``app.project.activeSequence.markers.getFirstMarker().getWebLinkFrameTarget()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkFrameTarget()``

**描述**
从标记的FrameTarget字段中检索帧目标。

**参数**
无.

**返回**
返回包含帧目标的“字符串”，如果失败，则返回**0**。

----
## Marker.getWebLinkURL()
|   ``app.project.activeSequence.markers.getFirstMarker().getWebLinkURL()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkURL()``

**描述**
从标记的URL字段检索URL。

**参数**
无.

**返回**
返回包含URL的“字符串”，如果失败，则返回**0**。

----
## Marker.setColorByIndex()
|   ``app.project.activeSequence.markers.getFirstMarker().setColorByIndex(colorIndex, markerIndex)``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setColorByIndex(colorIndex, markerIndex)``

    此功能是在Adobe Premire Pro 13.x中添加的。

**描述**
按索引设置标记颜色。下面列出的颜色索引。

* 0 = Green
* 1 = Red
* 2 = Purple
* 3 = Orange
* 4 = Yellow
* 5 = White
* 6 = Blue
* 7 = Cyan

**参数**

| 参数            | 类型        | 描述                                       |
| --------------- | ----------- | ------------------------------------------ |
| ``colorIndex``  | ``Integer`` | 要应用于标记的颜色索引。 |
| ``markerIndex`` | ``Integer`` | 要设置的标记的索引。             |

**返回**
Returns ``undefined``.

----
## Marker.setTypeAsChapter()
|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsChapter()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsChapter()``

**描述**
将标记类型设置为“章节”。

**参数**
无.

**返回**
如果成功则返回**0**。

----
## Marker.setTypeAsComment()
|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsComment()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsComment()``

**描述**
将标记的类型设置为“注释”。

**参数**
无.

**返回**
如果成功则返回**0**。

----
## Marker.setTypeAsSegmentation()
|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsSegmentation()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsSegmentation()``

**描述**
将标记类型设置为“分段”。

**参数**
无.

**返回**
如果成功则返回**0**。

----
## Marker.setTypeAsWebLink()
|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsWebLink()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsWebLink()``

**描述**
将标记的类型设置为“WebLink”。

**参数**
无.

**返回**
如果成功则返回**0**。
