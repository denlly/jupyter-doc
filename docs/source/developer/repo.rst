.. _developer-guide:

Jupylab开发指南是开发 Jupylab 扩展 (extensions) 或开发 Jupylab 自身。

General Codebase Orientation
----------------------------

 ``jupyterlab/jupyterlab`` 包含两个 package 的声明:

-  在 repo 的根目录中的 ``package.json``文件指示的是 npm 包

-  在repo的根目录中的 ``setup.py``文件指示的是Python包
npm包和Python包都命名为 ``jupyterlab``.

请查看 `Contributing
Guidelines <https://github.com/jupyterlab/jupyterlab/blob/master/CONTRIBUTING.md>`__
开发安装说明

项目文件夹 (Directories) 说明
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NPM package: ``src/``, ``lib/``, ``typings/``, ``buildutils/``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  ``src/``: Typescript 源文件.

   -  ``jlpm run build`` build 源文件，将build后的文件放入 ``lib/`` 文件夹里.
   -  ``jlpm run clean``删除 ``lib/`` 里的文件.

-  ``typings/``: 外部Typescript 的 library 定义的类型
   needs.
-  ``buildutils/``: 管理 repo 的 build 过程

实例: ``examples/``
^^^^^^^^^^^^^^^^^^^^^^^

``examples/`` 目录包含组件的独立示例，例如页面上的简单笔记本，控制台，终端和文件浏览器。 ``lab`` 示例说明了 JupyterLab中使用的组件的简化组合。 此示例显示多个独立组件组合在一起以创建更复杂的应用程序。

测试: ``test/``
^^^^^^^^^^^^^^^^^^

测试存储并在 ``test/``目录中运行。 源文件位于``test/src/``中。

Notebook extension: ``jupyterlab/``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

 ``jupyterlab/`` 目录包含Jupyter服务器扩展。

服务器扩展包括一个私有的npm包，以便构建扩展服务的 **webpack bundle** 。 私有npm包依赖于 repo 根目录中的 jupyterlab npm包。

Git hooks: ``git-hooks/``
^^^^^^^^^^^^^^^^^^^^^^^^^

 ``git-hooks/`` 目录存储了一些方便的git hooks，每次你在git repo中签出或合并（通过pull请求或直接push到master）时，它会自动重建npm包和服务器扩展。

Documentation: ``docs/``
^^^^^^^^^^^^^^^^^^^^^^^^

在构建文档（ ``jlpm run docs`` ）之后， ``docs / index.html`` 就是了
文档的入口点。