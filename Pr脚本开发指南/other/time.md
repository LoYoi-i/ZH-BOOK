# Time object
``myTime = new Time();``

**描述**
表示时间的对象。在内部，时间以``ticks``计算；每秒有254016000000次。该时间可以以不同的表示方式访问，包括作为时间代码字符串。

----

# Attributes 属性

----
## Time.seconds
``myTime.seconds``

**描述**
时间值，以秒表示。

**类型**
Number.

----
## Time.ticks
``myTime.ticks``

**描述**
时间值，以记号表示。

**类型**
String.

----

# Methods 方法

----
## Time.getFormatted()
``myTime.getFormatted(frameRate, displayFormat)``

**描述**
以字符串形式返回传递的``time``值，格式为指定的显示格式。

**参数**

| 参数              | 类型     | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ----------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``frameRate``     | ``Time`` | 要使用的帧速率的时间对象。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ``displayFormat`` | ``int``  | 要使用的显示格式。将是以下之一:<br>TIMEDISPLAY_24Timecode= 100;<br>TIMEDISPLAY_25Timecode = 101;<br>TIMEDISPLAY_2997DropTimecode = 102;<br>TIMEDISPLAY_2997NonDropTimecode = 103;<br>TIMEDISPLAY_30Timecode = 104;<br>TIMEDISPLAY_50Timecode = 105;<br>TIMEDISPLAY_5994DropTimecode = 106;<br>TIMEDISPLAY_5994NonDropTimecode = 107;<br>TIMEDISPLAY_60Timecode = 108;<br>TIMEDISPLAY_Frames = 109;<br>TIMEDISPLAY_23976Timecode = 110;<br>TIMEDISPLAY_16mmFeetFrames = 111;<br>TIMEDISPLAY_35mmFeetFrames = 112;<br>TIMEDISPLAY_48Timecode = 113;<br>TIMEDISPLAY_AudioSamplesTimecode = 200;<br>TIMEDISPLAY_AudioMsTimecode = 201; |

**返回**
A ``String``.

----
## Time.setSecondsAsFraction()
``myTime.setSecondsAsFraction(numerator, denominator)``

**描述**
将时间对象设置为分子除以分母的结果。

**参数**
分子和分母都是 ``ints``.

**返回**
Boolean; ``true`` 如果成功。
