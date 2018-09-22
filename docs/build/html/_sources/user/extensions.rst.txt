.. _user_extensions:

扩展
----------

从根本上说，JupyterLab的设计是可扩展的。 JupyterLab扩展可以自定义或增强JupyterLab的任何部分。 他们可以为 Notebook 中的丰富输出提供新的皮肤，文件查看器和编辑器或渲染器。 扩展可以将项添加到菜单或命令选项板，键盘快捷键或设置系统中的设置。 扩展可以为其他扩展提供API，并且可以依赖于其他扩展。 事实上，整个JupyterLab 本身只是一个扩展的集合，它们不比任何自定义扩展有更多的强大。

JupyterLab 采用npm包（Javascript开发中的标准包格式）进行扩展。 在GitHub上构建了许多社区开发的扩展。 您可以搜索GitHub主题 `jupyterlab-extension  
<https://github.com/topics/jupyterlab-extension>`__ 来查找扩展名。 有关开发扩展的信息，请参阅 :ref:`开发人员文档
<developer_extensions>` 。


.. note::

   如果您是JupyterLab 扩展开发人员，请注意扩展开发人员API不稳定，并且会不断更新。

要安装JupyterLab扩展，您需要安装Node.js版本4或更高版本。
如果您使用 ``conda``，您可以使用：

.. code:: bash

    conda install -c conda-forge nodejs

如果你的操作系统是 MacOS，可以通过 `Homebrew <https://brew.sh/>`__  安装:

.. code:: bash

    brew install node

您也可以`Node.js website <https://nodejs.org/>`__ 的官网下载 Node.js，并且安装。

安装扩展
~~~~~~~~~~~~~~~~~~~~~

The base JupyterLab application includes a core set of extensions, which
provide the features described in this user guide (notebook, terminal,
text editor, etc.) You can install new extensions into the application
using the command:

JupyterLab application 包含一组核心扩展，提供本用户指南（notebook，终端，文本编辑器等）中描述的功能。您可以使用以下命令在应用程序中安装新扩展：

.. code:: bash

    jupyter labextension install my-extension


其中``my-extension``是 `npm <https://www.npmjs.com>`__ 上有效的JupyterLab扩展名npm包的名称。 使用my-extension @ version语法安装特定版本的扩展，例如：

.. code:: bash

    jupyter labextension install my-extension@1.2.3

您还可以安装未上传到npm的扩展，即``my-extension``可以是包含扩展名，gzip压缩包或gzip压缩包的URL的本地目录。

我们鼓励扩展作者将``jupyterlab-extension`` 添加到任何具有JupyterLab扩展名的GitHub存储库，以便于发现。 您可以通过在GitHub中搜索`jupyterlab-extension <https://github.com/search?utf8=%E2%9C%93&q=topic%3Ajupyterlab-extension&type=Repositories>`__ 主题来查看扩展列表。

您可以通过运行以下命令列出当前安装的扩展：

.. code:: bash

    jupyter labextension list

通过运行以下命令卸载扩展：

.. code:: bash

    jupyter labextension uninstall my-extension

其中 ``my-extension`` 是扩展名，打印在扩展名列表中。 您也可以使用此命令卸载核心扩展（您可以随时重新安装核心扩展）。

安装和卸载扩展可能需要一些时间，因为它们已下载，与核心扩展捆绑在一起，整个应用程序将 *Rebuild* 。 您可以通过在 ``install`` 命令后列出其名称来在同一命令中安装/卸载多个扩展。


If you are installing/uninstalling several extensions in several stages,
you may want to defer rebuilding the application by including the flag
``--no-build`` in the install/uninstall step. Once you are ready to
rebuild, you can run the command:

如果要在几个阶段中安装/卸载多个扩展，则可能需要通过在安装/卸载步骤中包含标志``--no-build``来推迟重建应用程序。 准备好Rebuid后，可以运行以下命令：


.. code:: bash

    jupyter lab build

禁用扩展程序
~~~~~~~~~~~~~~~~~~~~

您可以通过运行以下命令禁用特定的JupyterLab扩展（包括核心扩展），而无需Rebuild应用程序：

.. code:: bash

    jupyter labextension disable my-extension

这将阻止扩展程序在浏览器中加载，但不需要Rebuild。

您可以使用以下命令重新启用扩展：

.. code:: bash

    jupyter labextension enable my-extension

高级用法
~~~~~~~~~~~~~~

JupyterLab持久存储的任何信息都存储在其应用程序目录中，包括设置和构建资产。 这与安装Python包的位置（例如在``site_packages``中）是分开的，因此安装目录是不可变的。

可以在任何JupyterLab命令中使用 ``--app-dir`` 覆盖应用程序目录，也可以通过设置JUPYTERLAB_DIR环境变量来覆盖应用程序目录。 如果未指定，则默认为``<sys-prefix>/share/jupyter/lab``，其中<sys-prefix>是当前Python环境的特定于站点的目录前缀。 您可以通过运行 ``jupyter lab path`` 来查询当前的应用程序路径。

JupyterLab Build 过程
^^^^^^^^^^^^^^^^^^^^^^^^

要 rebuild app目录，请运行``jupyter lab build``。 默认情况下，``jupyter labextension install` 命令构建应用程序，因此您通常不需要直接调用``build`` 。

Build 过程包括:

- 使用模板文件填充``staging\``目录
- 处理任何本地安装的包
- 确保所有已安装的资源（assets）都可用
- 打包资源（assets）
- 将打包的资源（assets）复制到``static``目录

Note that building will always use the latest JavaScript packages that meet
the dependency requirements of JupyterLab itself and any installed extensions.
If you wish to run JupyterLab with the set of pinned requirements that was
shipped with the Python package, you can launch as `jupyter lab --core-mode`.

请注意，构建将始终使用最新的JavaScript包，以满足JupyterLab本身和任何已安装扩展的依赖性要求。 如果您希望使用Python包附带的一组固定需求运行JupyterLab，您可以启动为`jupyter lab --core-mode`。

JupyterLab app 目录
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

JupyterLab应用程序目录包含子目录``extensions``, ``schemas``, ``settings``, ``staging``, ``static``, and
``themes``。

.. _extensions-1:

extensions
''''''''''

``extensions`` 目录包含应用程序的每个已安装扩展的打包tarball。 如果应用程序目录与``sys-prefix``目录不同，则``sys-prefix``目录中安装的扩展将在app目录中使用。 如果在``sys-prefix``目录中存在的app目录中安装了扩展，则它将隐藏``sys-prefix``版本。 卸载扩展将首先卸载带阴影的扩展，然后再次调用时尝试卸载``sys-prefix``版本。 如果无法卸载``sys-prefix``版本，则仍可使用设置中的``ignoredPackages``元数据忽略其插件。

schemas
'''''''

``schemas`` 目录包含描述各个扩展使用的设置的 `JSON
Schemas <http://json-schema.org/>`__ 。 用户可以使用JupyterLab设置编辑器编辑这些设置。

settings
''''''''

``settings``目录包含 ``page_config.json`` 和``build_config.json``文件。

.. _page_configjson:

page_config.json

``page_config.json`` 数据用于向应用程序环境提供配置数据。

 ``page_config.json`` 文件中的两个重要字段可以控制加载哪些插件：

    1. ``disabledExtensions`` 表示根本不应加载的扩展名。
    2. 对于在某些内容需要之前不加载的扩展的``deferredExtensions``，无论它们是否将``autostart``设置为``true``。

每个字段的值是一个字符串数组。 对``disabledExtensions``和``deferredExtensions``中的模式执行以下检查序列。

- 如果在配置值和包名称之间发生相同的字符串匹配（例如，``“@jupyterlab/apputils-extension”``），则整个包被禁用（或延迟）。

- 如果字符串值被编译为正则表达式并且对包名称测试为正（例如，``“disabledExtensions”：[“@jupyterlab/apputils*$”]``），则整个包被禁用（或延迟）。

- 如果在配置值和包中的单个插件ID之间发生相同的字符串匹配（例如，``“disabledExtensions”：[“@jupyterlab/apputils-extension：settings”]``），则该特定插件被禁用（或延迟）。

- 如果将字符串值编译为正则表达式并对包中的单个插件ID进行正向测试（例如，``"disabledExtensions": ["^@jupyterlab/apputils-extension:set.*$"]``），则该特定插件 被禁用（或延期）。


.. _build_configjson:

build_config.json

``build_config.json``文件用于跟踪使用 ``jupyter labextension install <directory>`` 安装的本地目录，以及已明确卸载的核心扩展。 ``build_config.json`` 文件的示例是：

.. code:: json

    {
        "uninstalled_core_extensions": [
            "@jupyterlab/markdownwidget-extension"
        ],
        "local_extensions": {
            "@jupyterlab/python-tests": "/path/to/my/extension"
        }
    }

staging and static
''''''''''''''''''

``static`` 目录包含将由JuptyerLab应用程序加载的assets。 ``staging`` 目录用于创建构建，然后填充``staging``目录。


运行``jupyter lab``将尝试在应用程序目录中运行``static assets``（如果存在）。 您可以运行``jupyter lab --core-mode`` 来加载核心JupyterLab应用程序（即没有任何扩展的应用程序）。

themes
''''''

``themes`` 目录包含JupyterLab Themes 扩展的资源（例如CSS和图标）。
