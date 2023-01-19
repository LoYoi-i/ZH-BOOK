# Properties object
``app.properties``

**描述**
*add description here*

----

# Attributes 属性

无.

----

# Methods 方法

----
## Properties.clearProperty()
``app.properties.clearProperty()``

**描述**
*add description here*

**参数**
*add parameters here*

**返回**
*add return value/type here*

----
## Properties.doesPropertyExist()
``app.properties.doesPropertyExist(property)``

**描述**
检查首选项中是否存在给定属性。
**参数**

| 参数         | 类型       | 描述                |
| ------------ | ---------- | ------------------- |
| ``property`` | ``String`` | 要检查的属性 |


**返回**
``Boolean``.

**示例**
检查首选项中是否存在索引为10和99的标签：

    var property = 'BE.Prefs.LabelNames.10';
    var exists = app.properties.doesPropertyExist(property);
    alert('Property "' + property + '" exists: ' + exists.toString());

    property = 'BE.Prefs.LabelNames.99';
    exists = app.properties.doesPropertyExist(property);
    alert('Property "' + property + '" exists: ' + exists.toString());

----
## Properties.getProperty()
``app.properties.getProperty(property)``

**描述**
返回属性值。

**参数**

| 参数 | 类型 | 描述 |
| ---- | ---- | ---- |
``property`` | ``String``  |要获取值的属性

**返回**
``String``.

**示例**
获取给定索引处的标签名称：

    var labelIndex = 0;
    var property = 'BE.Prefs.LabelNames.' + labelIndex;

    if (app.properties.doesPropertyExist(property)) {
        alert(app.properties.getProperty(property));
    } else {
        alert('Property "' + property + '" does not exist');
    }

----
## Properties.isPropertyReadOnly()
``app.properties.isPropertyReadOnly(property)``

**描述**
检查用户是否可以覆盖给定属性。如果此类属性不存在，则返回``false``。

**参数**

| 参数         | 类型       | 描述                 |
| ------------ | ---------- | -------------------- |
| ``property`` | ``String`` | 要检查的属性。 |

**返回**
``Boolean``.

----
## Properties.setProperty()
``app.properties.setProperty(property, value, persistent, createIfNotExist)``

**描述**
设置属性值。 NOTE: 对于Premiere Pro首选项中使用的任何文件路径，必须使用尾随路径分隔符。

**参数**

| 参数                 | 类型        | 描述                                             |
| -------------------- | ----------- | ------------------------------------------------ |
| ``property``         | ``String``  | 要创建的属性                             |
| ``value``            | ``Any``     | 属性的值                           |
| ``persistent``       | ``Boolean`` | 是否应在会话之间保持if |
| ``createIfNotExist`` | ``Boolean`` | 如果该属性不存在，则应创建   |

**返回**
``null``.

**示例**
更改标签名称：
```js
    var labelIndex = 0;
    var property = 'BE.Prefs.LabelNamesX.' + labelIndex;
    
    var newValue = 'Changed via Script';
    var persistent = true;
    var createIfNotExist = true;

    if (app.properties.doesPropertyExist(property)) {
        if (app.properties.isPropertyReadOnly(property)) {
            alert('无法重命名属性 "' + property + '" because it is 只读.');
        } else {
            var oldValue = app.properties.getProperty(property);
            app.properties.setProperty(property, newValue, persistent, createIfNotExist);
            alert('值更改自 "' + oldValue + '" to "' + newValue + '"');
        }
    } else {
        app.properties.setProperty(property, newValue, persistent, createIfNotExist);
        alert('已创建新属性 "' + property + '" with value "' + newValue + '"');
    }
```