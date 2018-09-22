.. _jupyterlab:

JupyterLab on JupyterHub
------------------------

JupyterLab与JupyterHub一起开箱即用，甚至可以与经典Notebook并排运行。

默认情况下使用JupyterLab
~~~~~~~~~~~~~~~~~~~~~~~~~

如果在运行JupyterHub的系统上安装JupyterLab，它将立即在 ``/lab`` URL上可用，但默认情况下用户仍将被定向到经典Notebook（``/tree``）。 要将用户的默认用户界面更改为JupyterLab，请在jupyterhub_config.py文件中设置以下配置选项：
:file:`jupyterhub_config.py` file::

    c.Spawner.default_url = '/lab'

在此配置中，用户仍然可以在``/tree``访问经典Notebook，方法是在浏览器中键入该URL，或者使用JupyterLab的“帮助”菜单中的 “Launch Classic Notebook” 项。

进一步整合
~~~~~~~~~~~~~~~~~~~

JupyterLab和JupyterHub之间的额外集成由JupyterLab的 `jupyterlab-hub <https://github.com/jupyterhub/jupyterlab-hub>`__ 扩展提供。 它提供了一个Hub菜单，其中包含访问JupyterHub控制面板或注销集线器的项目。

安装 ``jupyterlab-hub`` extension, 执行::

    jupyter labextension install @jupyterlab/hub-extension

`jupyterlab-hub GitHub repository
<https://github.com/jupyterhub/jupyterlab-hub>`__ 存储库提供了进一步的说明。

示例配置
~~~~~~~~~~~~~~~~~~~~~

有关将JupyterLab与JupyterHub一起使用的完整配置示例，请参阅`jupyterhub-deploy-teaching
<https://github.com/jupyterhub/jupyterhub-deploy-teaching>`__ 存储库。