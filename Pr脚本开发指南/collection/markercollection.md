# MarkerCollection object
|   ``app.project.sequences[index].markers``
|   ``app.project.rootItem.children[index].getMarkers()``

The MarkerCollection object represents a collection of `Marker objects <marker>` in a `projectItem` and `sequence`. 

MarkerCollection is a subclass of `collection`. All methods and attributes of Collection, in addition to those listed below, are available when working with MarkerCollection.

----

# Attributes 属性

----
## MarkerCollection.numMarkers
|   ``app.project.sequences[index].markers.numMarkers``
|   ``app.project.rootItem.children[index].getMarkers().numMarkers``

**描述**
The count of marker objects in the project item or sequence.

**类型**
Integer, 只读.

----

# Methods 方法

----
## MarkerCollection.createMarker()
|   ``app.project.sequences[index].markers.createMarker(time)``
|   ``app.project.rootItem.children[index].getMarkers().createMarker(time)``

**描述**
在项目项或序列上创建新的``标记``。

**参数**

| 参数     | 类型      | 描述                                                |
| -------- | --------- | --------------------------------------------------- |
| ``time`` | ``Float`` | 应创建标记的时间（秒）. |

**返回**
`marker` if successful.

----
## MarkerCollection.deleteMarker()
|   ``app.project.sequences[index].markers.deleteMarker(marker)``
|   ``app.project.rootItem.children[index].getMarkers().deleteMarker(marker)``

**描述**
从集合中删除给定的标记对象。

**参数**

| 参数       | 类型     | 描述                                       |
| ---------- | -------- | ------------------------------------------ |
| ``marker`` | `marker` | 要从集合中删除的标记对象. |

**返回**
``Boolean``.

**Examples**
从活动序列中删除所有标记

    var markers = app.project.activeSequence.markers;
    var marker = markers.getFirstMarker();
    var count = markers.numMarkers;

    while (marker) {
        markers.deleteMarker(marker);
        marker = markers.getFirstMarker();
    }

    alert('Removed ' + count.toString() + ' markers');

----
## MarkerCollection.getFirstMarker()

|   ``app.project.sequences[index].markers.getFirstMarker()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker()``

**描述**
检索给定项目项或序列上的第一个标记对象，按时间（秒）排序.

**参数**
无.

**返回**
`marker` or ``undefined``.

----
## MarkerCollection.getLastMarker()
|   ``app.project.sequences[index].markers.getLastMarker()``
|   ``app.project.rootItem.children[index].getMarkers().getLastMarker()``

**描述**
检索给定项目项或序列的最后一个标记对象，按时间（秒）排序.

**参数**
无.

**返回**
`marker` or ``undefined``.

----
## MarkerCollection.getNextMarker()
|   ``app.project.sequences[index].markers.getNextMarker(currentMarker)``
|   ``app.project.rootItem.children[index].getMarkers().getNextMarker(currentMarker)``

**描述**
获取下一个可用标记，按秒排序，从给定标记开始.

**参数**

| 参数              | 类型     | 描述                                                    |
| ----------------- | -------- | ------------------------------------------------------- |
| ``currentMarker`` | `marker` | 开始标记对象，从中获取下一个标记. |

**返回**
`marker` or ``undefined``.

----
## MarkerCollection.getPrevMarker()
|   ``app.project.sequences[index].markers.getPrevMarker(currentMarker)``
|   ``app.project.rootItem.children[index].getMarkers().getPrevMarker(currentMarker)``

**描述**
获取上一个可用标记，按秒排序，从给定标记开始.

**参数**

| 参数              | 类型     | 描述                                                        |
| ----------------- | -------- | ----------------------------------------------------------- |
| ``currentMarker`` | `marker` | 起始标记对象，从中获取上一个标记. |

**返回**
`marker` or ``undefined``.
