# AudioChannelMapping object
``app.project.rootItem.children[index].getAudioChannelMapping``

**描述**
AudioChannelMapping 对象定义应用于给定``projectItem``的音频通道映射。

----

# Attributes 属性

----
## AudioChannelMapping.audioChannelsType
``app.project.rootItem.children[index].getAudioChannelMapping.audioChannelsType``

**描述**
此频道中包含的音频类型。将为0、1或2，对应于 ``AUDIOCHANNELTYPE_Mono``, ``AUDIOCHANNELTYPE_Stereo``, or ``AUDIOCHANNELTYPE_51``.

----
## AudioChannelMapping.audioClipsNumber
``app.project.rootItem.children[index].getAudioChannelMapping.audioClipsNumber``

**描述**
与此音频频道关联的音频剪辑数。

----

# Methods 属性

----
## AudioChannelMapping.setMappingForChannel()
``app.project.rootItem.children[index].setMappingForChannel(channelIndex, sourceChannelIndex)``

**描述**
将源频道映射到指定的频道索引。 

**参数**
| 参数                   | 类型        | 描述                                  |
| ---------------------- | ----------- | ------------------------------------- |
| ``channelIndex``       | ``Integer`` | 要映射的通道的索引。  |
| ``sourceChannelIndex`` | ``Integer`` | 要映射的源频道的索引。 |

**返回**
如果成功则返回 **true**，如果不支持该映射则返回 **false**。
