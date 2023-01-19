# Overview


Premiere Pro提供了一个ExtendeScript API，允许访问和操作大多数项目元素，包括元数据、导出和渲染选项。

note:: 本文档不介绍ExtendeScript、ExtendeScript调试或其他开发技术。它着重于Premiere Pro ExtendeScript API和脚本的执行上下文。

Premiere Pro ExtendeScript API最初并不完整，仅用于内部测试，但多年来一直在稳步增长。截至12.1.1（截至本文撰写之时的当前版本），API提供了对所有项目元素以及应用程序设置的全面访问（通常是控制）。


# Example code
------------

PProPanel示例练习Premiere Pro的ExtendeScript API： https://github.com/Adobe-CEP/Samples/tree/master/PProPanel.


开发和调试工具
-------------------------------
Adobe不再更新ExtendeScript Toolkit（ESTK）；ExtendeScript的推荐调试环境是Microsoft Visual Studio Code，带有Adobe的ExtendeScript调试extension:https://marketplace.visualstudio.com/items?itemName=Adobe.extendscript-debug


