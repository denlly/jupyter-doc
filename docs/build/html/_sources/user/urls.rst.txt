.. _urls:

JupyterLab URLs
---------------

与经典笔记本一样，JupyterLab为用户提供了一种复制打开特定笔记本或文件的URL的方法。 此外，JupyterLab URLs是用户界面的高级部分，允许管理工作区。 这两个函数 - 文件路径和工作空间 - 可以 :ref:`组合在打开特定工作空间中特定文件的URL中<url-combine>`。
.. _url-tree:

文件导航 ``/tree``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

JupyterLab的文件导航URL采用经典笔记本的命名法; 这些URL是 ``/tree`` URLs:
.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/tree/path/to/notebook.ipynb


输入此URL将以 :ref:`单文档模式 <tabs>` 在 JupyterLab 中打开笔记本。

.. _url-workspaces:

管理工作区
~~~~~~~~~~~~~~~~~~~

JupyterLab 会话始终驻留在工作空间中。 工作区包含 JupyterLab 的状态：当前打开的文件，应用程序区域和选项卡的布局等。刷新页面时，将还原工作区。

默认工作空间未命名，仅将其状态保存在用户的本地浏览器中：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab

命名工作区将其状态保存在服务器上，并且可以在多个用户（或浏览器）之间共享，只要他们可以访问同一服务器：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/foo


工作区应该一次只能在一个浏览器选项卡中打开。 如果JupyterLab检测到同时多次打开工作空间，则会提示输入新的工作空间名称。 同时也不支持在两个不同的浏览器选项卡中打开文档。

.. _url-clone:

克隆工作区
~~~~~~~~~~~~~~~~~~

您可以使用 ``clone`` url参数将工作空间的内容复制到另一个工作空间。

要将工作区 ``foo`` 的内容复制到工作区 ``bar`` 中：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/bar?clone=foo

要将默认工作空间的内容复制到工作空间 ``foo`` 中：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/foo?clone

要将工作空间 ``foo`` 的内容复制到默认工作空间：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab?clone=foo

.. _url-reset:

重置工作区
~~~~~~~~~~~~~~~~~~~~~

使用 ``reset`` url参数清除其内容的工作空间。

要重置工作空间 ``foo`` 的内容：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/foo?reset

要重置默认工作区的内容：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/lab?reset

.. _url-combine:

组合URL功能
~~~~~~~~~~~~~~~~~~~~~~~

这些URL功能可以单独使用，如上所述，也可以组合使用。

要重置工作区 ``foo`` 并在以后加载特定 notebook：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/foo/tree/path/to/notebook.ipynb?reset

要将工作区栏的内容克隆到工作区 ``foo`` 中，然后加载 notebook ：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/workspaces/foo/tree/path/to/notebook.ipynb?clone=bar


要重置默认工作区的内容并加载 notebook：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab/tree/path/to/notebook.ipynb?reset
