.. _interface:

JupyterLab 接口 (API)
--------------------------------

JupyterLab 为交互式探索性计算提供灵活的构建块。虽然 JupyterLab 具有传统集成开发环境（IDE）中的许多功能，但它仍然专注于交互式探索性计算。

JupyterLab 界面包含一个 :ref:`主工作区 <main-area>` ，包含文档和活动选项卡，可折叠 :ref:`左侧边栏 <left-sidebar>` 和 :ref:`菜单栏 <menu-bar>`。 左侧边栏包含 :ref:`文件浏览器 <working-with-files>` ，正在运行的 :ref:`内核和终端列表 <running>` ，:ref:`命令选项板<commands>` ， :ref:`笔记本单元工具检查器 <notebook>` 和 :ref:`选项卡列表 <tabs>` 。

.. image:: images/interface_jupyterlab.png
   :align: center
   :class: jp-screenshot

JupyterLab 会话始终驻留在 :ref:`工作空间中 <url-workspaces>`。 工作区包含JupyterLab的状态：当前打开的文件，应用程序区域和选项卡的布局等。工作区可以使用命名工作区URL保存在服务器上。 要了解有关Jupyterlab中URL的更多信息，请访问 :ref:`urls`。

.. _menu-bar:

菜单栏 (Menu Bar)
~~~~~~~~

JupyterLab顶部的菜单栏有一个顶级菜单，允许您通过键盘快捷键显示 JupyterLab 中可用的操作。 默认菜单是：

-  **File**: 与文件和目录相关的操作
-  **Edit**: 与编辑文件和其他活动有关的行动
-  **View**: 改变 JupyterLab 外观的动作
-  **Run**: 用于在不同活动中运行代码的操作，例如 notebooks 和 consoles
-  **Kernel**: 用于管理内核的操作，内核是用于运行代码的单独进程
-  **Tabs**: 停靠面板中的打开文档和活动列表
-  **Settings**: 常用设置和高级设置编辑器
-  **Help**: JupyterLab 和内核帮助链接列表

:ref:`JupyterLab extensions <user_extensions>` 还可以在菜单栏中创建新的顶级菜单.

.. _left-sidebar:

左侧边栏 (Left Sidebar)
~~~~~~~~~~~~

左侧边栏包含许多常用选项卡，例如文件浏览器，正在运行的内核和终端列表，命令选项板以及主工作区中的选项卡列表：

.. image:: images/interface_left.png
   :align: center
   :class: jp-screenshot

.. _left-sidebar-toggle:

通过在“视图”菜单中选择“显示左侧边栏”或单击活动侧边栏选项卡，可以折叠或展开左侧边栏：


.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/PlJGecfetek?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

JupyterLab 扩展可以向左侧边栏添加其他面板。

.. _main-area:

主工作区 (Main Work Area)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _main-area-vid:

JupyterLab中的 主工作区 使您可以将文档（notebooks，文本文件等）和其他活动（terminals，code consoles等）排列到可以调整大小或细分的选项卡面板中。 将选项卡拖动到选项卡面板的中心可将选项卡移动到面板。 通过将选项卡拖动到面板的左侧，右侧，顶部或底部来细分选项卡面板：

.. raw:: html

  <div class="jp-youtube-video">
    <iframe src="https://www.youtube-nocookie.com/embed/Ka8qS7CO1XQ?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

工作区域只有一个当前活动。 当前活动的选项卡标有彩色顶部边框（默认为蓝色）。

.. _tabs:

标签 (tabs) 和单文档模式
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

左侧栏中的“选项卡”面板列出了主要工作区中的打开文档或活动：

.. image:: images/interface_tabs.png
   :align: center
   :class: jp-screenshot

选项卡菜单中也提供了相同的信息：

.. image:: images/interface_tabs_menu.png
   :align: center
   :class: jp-screenshot

.. _tabs-singledocument:

在不关闭主工作区域中的其他选项卡的情况下，关注单个文档或活动通常很有用。 单文档模式启用此功能，同时可以轻松返回主工作区中的多活动布局。 使用“视图”菜单切换单文档模式：

.. raw:: html

  <div class="jp-youtube-video">
    <iframe src="https://www.youtube-nocookie.com/embed/DO7NOenMQC0?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

离开单文档模式时，将恢复主区域的原始布局。

上下文菜单 (Context Menus)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _context-menus-rightclick:

JupyterLab 的许多部分（例如 notebooks，文本文件，code consoles 和选项卡）都有上下文菜单，可以通过右键单击元素来访问它们：

.. raw:: html

  <div class="jp-youtube-video">
    <iframe src="https://www.youtube-nocookie.com/embed/y30fs6kg6fc?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _context-menus-shiftrightclick:

可以通过按住``Shift`` 和右键单击来访问浏览器的本机上下文菜单：:

.. raw:: html

  <div class="jp-youtube-video">
    <iframe src="https://www.youtube-nocookie.com/embed/XPPWW-7WJ40?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _shortcuts:

键盘快捷键
~~~~~~~~~~~~~~~~~~

.. _shortcuts-settings:

与经典 Notebook 一样，您可以通过键盘快捷键导航用户界面。 您可以通过选择“设置”菜单中的“高级设置编辑器”项，然后在“设置”选项卡中选择“键盘快捷键”来查找和自定义当前键盘快捷键列表。

.. raw:: html

    <div class="jp-youtube-video">
       <iframe src="https://www.youtube-nocookie.com/embed/rhW3kAExCik?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>

.. _editor-keymaps:

您还可以使用“设置”菜单中的“:ref:` 文本编辑器<file-editor>` 键映射”子菜单自定义文本编辑器以使用vim，emacs或Sublime Text键盘映射：

.. raw:: html

    <div class="jp-youtube-video">
       <iframe src="https://www.youtube-nocookie.com/embed/COheO7sA4-U?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
