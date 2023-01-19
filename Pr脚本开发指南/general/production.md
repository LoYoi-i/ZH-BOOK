#Production object
``app.production``

**描述**
Production对象允许ExtendeScript访问和操作产品、插入项目、创建新项目和垃圾箱，以及将现有的Production项目移动到垃圾箱。

----

# Attributes 属性

----
## Production.name-
``app.production.name``

**描述**
产品的名称。

**类型**
String.

----
## Production.path
``app.production.path``

**描述**
Production文件夹的路径。

**类型**
String.

----
## Production.projects
``app.production.projects``

**描述**
生产中包含的一系列项目，这些项目当前处于打开状态。不包括非开放项目。

**类型**
:ref:`projectCollection`, 只读.

----

# Methods 方法

----
## Production.addProject()
``app.production.addProject(srcProjectPath, destProjectPath)``

**描述**
将项目从其他位置复制到Production目录中。

**参数**

| 参数                | 类型       | 描述                 |
| ------------------- | ---------- | -------------------- |
| ``srcProjectPath``  | ``String`` | 源项目的路径。       |
| ``destProjectPath`` | ``String`` | 添加项目的目标路径。 |

**返回**
如果成功，则返回**true**。

----
## Production.close()
``app.production.close()``

**描述**
关闭生产以及该生产中所有打开的项目。

**参数**
无.

**返回**
如果成功，则返回**true**。

----
## Production.getLocked()
``app.production.getLocked()``

**描述**
返回Production的当前锁定状态。

**参数**
无.

**返回**
如果生产被锁定，则返回**true**；如果生产被解锁，则返回**false**。

----
## Production.moveToTrash()
``app.production.moveToTrash(projectOrFolderPath, suppressUI, saveProject)``

**描述**
将指定的路径（"bin"）或.prproj移动到Production的垃圾箱文件夹中。

**参数**

| 参数                    | 类型        | 描述                     |
| ----------------------- | ----------- | ------------------------ |
| ``projectOrFolderPath`` | ``String``  | 源项目的路径。           |
| ``suppressUI``          | ``Boolean`` | 是否抑制任何生成的对话。 |
| ``saveProject``         | ``Boolean`` | 是否先保存项目。         |

**返回**
如果成功，则返回**true**。

----
## Production.setLocked()
``app.production.setLocked(locked)``

**描述**
设置生产的锁定状态

**参数**

| 参数       | 类型        | 描述             |
| ---------- | ----------- | ---------------- |
| ``locked`` | ``Boolean`` | 所需的锁定状态。 |

**返回**
如果成功，则返回**true**。
