Anywhere object
==========================
``app.anywhere``

**描述**
**anywhere**对象表示任何可用的Adobe anywhere或Team Projects服务器。

----
# Attributes 属性

无.

----

# Methods 方法

----
## Anywhere.getAuthenticationToken()
``app.anywhere.getAuthenticationToken()``

**描述**
检索身份验证令牌。

**参数**
无.

**返回**
包含登录令牌的**字符串**，如果失败，则为**0**.

----
## Anywhere.getCurrentEditingSessionActiveSequenceURL()
``app.anywhere.getCurrentEditingSessionActiveSequenceURL()``

**描述**
检索生产中当前活动序列的URL.

**参数**
无.

**返回**
返回包含资产URL的**字符串**，如果失败（包括没有活动序列或没有打开编辑会话），则返回**0**.

----
## Anywhere.getCurrentEditingSessionSelectionURL()
``app.anywhere.getCurrentEditingSessionSelectionURL()``

**描述**
检索当前所选单个资产的URL。如果选择了多个或多个项目，将失败.

**参数**
无.

**返回**
返回包含资产URL的**字符串**，如果失败，返回**0**（包括选择了多个或少个项目）.

----
## Anywhere.getCurrentEditingSessionURL()
``app.anywhere.getCurrentEditingSessionURL()``

**描述**
检索当前正在编辑的产品的URL.

**参数**
无.

**返回**
返回包含生产URL的**字符串**，如果不成功，则返回**0**.

----
## Anywhere.isProductionOpen()
``app.anywhere.isProductionOpen()``

**描述**
检索Anywhere或Team Projects生产当前是否打开.

**参数**
无.

**返回**
如果生产已打开，则返回``true`` ``false ``如果不是.

----
## Anywhere.listProductions()
``app.anywhere.listProductions()``

**描述**
检索当前服务器上当前用户可用的生产名称. 

**参数**
无.

**返回**
返回包含可飞行产品名称的**字符串**数组，如果失败，返回**0**.

----
## Anywhere.openProduction()
``app.anywhere.openProduction(productionURL)``

**描述**
在指定的URL打开生产。

**参数**

| 参数              | 类型       | 描述                               |
| ----------------- | ---------- | ---------------------------------- |
| ``productionURL`` | ``String`` | 要打开的产品的url。 |


**返回**
如果成功则返回**0**。

----
## Anywhere.setAuthenticationToken()
``app.anywhere.setAuthenticationToken(token, emailAddress)``

**描述**
使用提供的令牌将指定的电子邮件地址记录到服务器中。

**参数**

| 参数             | 类型       | 描述                          |
| ---------------- | ---------- | ----------------------------- |
| ``token``        | ``String`` | 授权令牌。       |
| ``emailAddress`` | ``String`` | 关联的电子邮件地址。 |

**返回**
如果成功则返回**0**。
