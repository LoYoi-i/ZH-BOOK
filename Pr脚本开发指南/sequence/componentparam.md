
ComponentParam object
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index]``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index]``

**描述**
**component parameter** 对象表示与组件关联的参数，应用于``trackItem``。

----

# Attributes 属性

----
## ComponentParam.displayName
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].displayName``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].displayName``

**描述**
显示给用户的组件参数的名称。本地化。

**类型**
String; 只读.

----

# Methods 方法

----
## ComponentParam.addKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].addKey(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].addKey(time)``

**描述**
在指定时间向组件参数流添加关键帧。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数     | 类型   | 描述                               |
| -------- | ------ | ---------------------------------- |
| ``time`` | `time` | 何时应添加关键帧。 |

**返回**
如果成功则返回**0**。

----
## ComponentParam.areKeyframesSupported()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].areKeyframesSupported()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].areKeyframesSupported()``

**描述**
检索此组件参数是否支持关键帧。

**参数**
无.

**返回**
如果支持关键帧，则返回``true``如果不是，则为``false``。

----
## ComponentParam.findNearestKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findNearestKey(timeToCheck, threshold)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findNearestKey(timeToCheck, threshold)``

**描述**
设置零部件参数是否随时间变化。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数            | 类型 | 描述                                                    |
| --------------- | ---- | ------------------------------------------------------- |
| ``timeToCheck`` |      | 从给定时间开始搜索                          |
| ``threshold``   |      | 任一方向上的时间距离，单位为**记号**。 |

**返回**
返回一个**时间**值，指示最近的关键帧的时间。

----
## ComponentParam.findNextKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findNextKey(timeToCheck)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findNextKey(timeToCheck)``

**描述**
返回所提供的``timeToCheck``之后的关键帧。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数            | 类型 | 描述                            |
| --------------- | ---- | ------------------------------- |
| ``timeToCheck`` |      | 从给定时间开始搜索。 |

**返回**
返回一个**Time**值，指示最近的关键帧的时间，如果没有可用的后续关键帧，则返回**0**。

----
## ComponentParam.findPreviousKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findPreviousKey(timeToCheck)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findPreviousKey(timeToCheck)``

**描述**
返回在时间上早于提供的``timeToCheck``的关键帧。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数            | 类型 | 描述                            |
| --------------- | ---- | ------------------------------- |
| ``timeToCheck`` |      | 从给定时间开始搜索。 |

**返回**
返回一个**Time**值，指示最近的关键帧的时间，如果没有可用的上一个关键帧，则返回**0**。

----
## ComponentParam.getColorValue()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getColorValue()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getColorValue()``

**描述**
获取组件参数流的值。注意：这只适用于非时变参数。

**参数**
无.

**返回**
返回包含在组件参数流中找到的值的**Color**，如果不成功，则返回**0**。

----
## ComponentParam.getKeys()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getKeys()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getKeys()``

**描述**
返回``timeToCheck``组件参数上所有关键帧的数组。注意：这只能在支持关键帧的参数上设置。

**参数**
无.

**返回**
返回 **时间** 值的**数组**，指示每个关键帧发生的时间，如果没有可用的关键帧，则返回**0**。

----
## ComponentParam.getValue()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValue()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValue()``

**描述**
获取组件参数流的值。注意：这只适用于非时变参数。

**参数**
无.

**返回**
返回组件参数流的值；返回随流类型而变化。

----
## ComponentParam.getValueAtKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValueAtKey(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValueAtKey(time)``

**描述**
在指定的关键帧时间检索组件参数流的值。注意：只能与可设置关键帧的参数流一起使用。

**参数**

| 参数     | 类型   | 描述                                                      |
| -------- | ------ | --------------------------------------------------------- |
| ``time`` | `time` | 检索关键帧值的时间。 |

**返回**
返回组件参数流在``时间``的值，如果失败，则返回**0**。

----
## ComponentParam.getValueAtTime()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValueAtTime(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValueAtTime(time)``

**描述**
在指定时间检索组件参数流的值。如果该值介于两个关键帧之间，则会进行插值。

**参数**

| 参数     | 类型   | 描述                                                      |
| -------- | ------ | --------------------------------------------------------- |
| ``time`` | `time` | 检索关键帧值的时间。 |

**返回**
返回组件参数流在``时间``的值，如果失败，则返回**0**。

----
## ComponentParam.isTimeVarying()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].isTimeVarying()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].isTimeVarying()``

**描述**
检索组件参数是否随时间变化。 

**参数**
无.

**返回**
如果参数随时间变化，则返回``true`` 如果不是，则为``false``。

----
## ComponentParam.removeKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].removeKey(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].removeKey(time)``

**描述**
在指定时间删除组件参数流上的关键帧。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数     | 类型   | 描述                                                          |
| -------- | ------ | ------------------------------------------------------------- |
| ``time`` | `time` | 时间值，指示何时应删除关键帧。 |

**返回**
如果成功则返回**0**。

----
## ComponentParam.removeKeyRange()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].removeKeyRange(startTime, endTime)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].removeKeyRange(startTime, endTime)``

**描述**
在指定时间之间从组件参数流中删除所有关键帧。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数          | 类型   | 描述                                                         |
| ------------- | ------ | ------------------------------------------------------------ |
| ``startTime`` | `time` | 开始移除关键帧的时间（含）。 |
| ``endTime``   | `time` | 结束关键帧移除的时间。               |

**返回**
如果成功则返回**0**。

----
## ComponentParam.setColorValue()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setColorValue(alpha, red, green, blue, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setColorValue(alpha, red, green, blue, updateUI)``

**描述**
设置组件参数流中的值，表示颜色。

**参数**

| 参数         | 类型        | 描述                                                       |
| ------------ | ----------- | ---------------------------------------------------------- |
| ``alpha``    | ``Integer`` | Alpha value.透明度                                               |
| ``red``      | ``Integer`` | Red value.红                                                 |
| ``green``    | ``Integer`` | Green value.绿                                               |
| ``blue``     | ``Integer`` | Blue value.蓝                                                |
| ``updateUI`` | ``Integer`` | 更新流的值后强制更新UI. |

**返回**
如果成功则返回**0**。

----
## ComponentParam.setInterpolationTypeAtKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setInterpolationTypeAtKey(time, interpretationType)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setInterpolationTypeAtKey(time, interpretationType)``

**描述**
指定要在指定时间指定给关键帧的插值类型。注意：只能与可设置关键帧的参数流一起使用。

**参数**

| 参数                   | 类型        | 描述                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``time``               | `time`      | 要修改的关键帧的时间。                                                                                                                                                                                                                                                                                                                                               |
| ``interpretationType`` | ``type``    | 必须是以下之一： <br>- 0 ``kfInterpMode_Linear``<br>- 1 ``kfInterpMode_EaseIn_Obsolete``<br>- 2 ``kfInterpMode_EaseOut_Obsolete``<br>- 3 ``kfInterpMode_EaseInEaseOut_Obsolete``<br>- 4 ``kfInterpMode_Hold``<br>- 5 ``kfInterpMode_Bezier``<br>- 6 ``kfInterpMode_Time``<br>- 7 ``kfInterpMode_TimeTransitionStart``<br>- 8 ``kfInterpMode_TimeTransitionEnd`` |
| ``updateUI``           | ``boolean`` | 之后是否更新UI。                                                                                                                                                                                                                                                                                                                                              |

**返回**
如果成功则返回**0**。

----
## ComponentParam.setTimeVarying()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setTimeVarying(varying)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setTimeVarying(varying)``

**描述**
设置零部件参数是否随时间变化。注意：这只能在支持关键帧的参数上设置。

**参数**

| 参数        | 类型        | 描述                                                                          |
| ----------- | ----------- | ----------------------------------------------------------------------------- |
| ``varying`` | ``Boolean`` | 如果为 ``true`` ，组件参数将随时间变化； 如果为``false``，则不会。 |

**返回**
如果成功则返回**0**。

----
## ComponentParam.setValue()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setValue(value, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setValue(value, updateUI)``

**描述**
设置组件参数流的值。注意：这只适用于非时变参数。

**参数**

| 参数         | 类型        | 描述                                                                                    |
| ------------ | ----------- | --------------------------------------------------------------------------------------- |
| ``value``    |             | 必须是组件参数流的适当类型。                     |
| ``updateUI`` | ``Integer`` | 如果``1``，将在更新流的值后强制Premiere Pro更新UI。 |

**返回**
如果成功则返回**0**。

----
## ComponentParam.setValueAtKey()
|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setValueAtKey(time, value, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setValueAtKey(time, value, updateUI)``

**描述**
在指定的关键帧时间设置组件参数流的值。注意：只能与可设置关键帧的参数流一起使用。

**参数**

| 参数         | 类型        | 描述                                                                                    |
| ------------ | ----------- | --------------------------------------------------------------------------------------- |
| ``time``     | `time`      | 应设置关键帧值的时间。                                       |
| ``value``    |             | 要设置的值。                                                                      |
| ``updateUI`` | ``Integer`` | 如果``1``，将在更新流的值后强制Premiere Pro更新UI。 |

**返回**
如果成功则返回**0**。
