.. _notebook:

Notebooks
---------

Jupyter notebooks 是将实时可运行代码与描述文本（Markdown），方程式（LaTeX），images，交互式可视化和其他丰富输出相结合的文档：

.. image:: images/notebook/notebook_ui.png
   :align: center
   :class: jp-screenshot


**JupyterLab完全支持Jupyter笔记本（.ipynb文件）。** JupyterLab中使用的笔记本文档格式与经典的Jupyter Notebook相同。 您现有的笔记本应该在JupyterLab中正确打开。 如果他们不这样做，请在我们的 `GitHub issues <https://github.com/jupyterlab/jupyterlab/issues>`__ 页面上打开一个问题。


.. _create-notebook:

单击文件浏览器中的 ``+`` 按钮，然后在新的Launcher选项卡中选择内核，创建一个笔记本：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/QL0IxDAOEc0?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _rename-file:

使用默认名称创建新文件。 通过在文件浏览器中右键单击其名称并从上下文菜单中选择“Rename”来重命名文件：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/y3xzXelypjs?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

JupyterLab 中 Notebooks 的用户界面紧跟经典 Jupyter Notebook 的用户界面。 经典笔记本的键盘快捷键继续工作（使用命令和编辑模式）。 但是，JupyterLab中的笔记本电脑可能会有许多新功能。

.. _drag-drop:

拖放单元格以重新排列笔记本：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/J9xoTGdqWIo?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _drag-copy:

在笔记本之间拖动单元格以快速复制内容：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/YTNZ5TS2LfU?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _multiple-views:

创建单个 notebook 的多个同步 views：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/SQn9aRc050w?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _collapse-code:

使用 View menu 或每个单元格左侧的蓝色伸缩按钮折叠并展开代码和输出：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/WgiX3ZRaTiY?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _enable-scrolling:

通过右键单击单元格并选择 “为输出启用滚动” ，启用长输出滚动：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/U4usAUZCv_c?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _cell-output-mirror:

创建单元格输出的新同步视图：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/Asa_ML45HP8?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _tab-completion:

选项卡完成（使用 ``Tab`` 键激活）现在可以包含有关匹配项类型的其他信息：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/MuNr0i8LgpM?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>


注意：IPython 6.3.1 暂时禁用了类型注释。 要重新启用它们，请将``c.Completer.use_jedi = True`` 添加到 `ipython_config.py <http://ipython.readthedocs.io/en/stable/development/config.html>`__ 文件中。

.. _tooltip:

工具提示（使用 ``Shift Tab`` 激活）包含有关对象的其他信息：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/TgqMK1SG7XI?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _create-console:

您可以将 :ref:`代码控制台 <code-console>` 连接到笔记本内核，以便按照完成它们的顺序在内核中完成计算日志。 附加的代码控制台还提供了交互式检查内核状态而无需更改笔记本的位置。 右键单击笔记本并选择“New Console for Notebook”：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/eq1l7DBngQQ?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>
