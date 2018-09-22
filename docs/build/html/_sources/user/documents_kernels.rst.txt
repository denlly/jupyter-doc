.. _kernel-backed-documents:

文件和内核
---------------------

在Jupyter体系结构中，内核是由服务器启动的独立进程，它以不同的编程语言和环境运行代码。 JupyterLab使您可以将任何打开的文本文件连接到 :ref:`代码控制台和内核<code-console>` 。 这意味着您可以交互式地从内核中的文本文件轻松运行代码。

.. _create-console:

右键单击文档，然后选择“Create Console for Editor”：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/JS2mhCD3rwE?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _send-code:

代码控制台打开后，发送一行代码或选择一段代码，然后通过按 ``Shift Enter`` 键将其发送到代码控制台：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/ODevllc9PXw?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

.. _run-markdown:

在Markdown文档中， ``Shift Enter`` 将自动检测光标是否在代码块内，如果没有选择则运行整个块：

.. raw:: html

  <div class="jp-youtube-video">
     <iframe src="https://www.youtube-nocookie.com/embed/Kz3e7SgqTnI?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

文本文件编辑器中的*任何*文本文件（Markdown，Python，R，LaTeX，C ++等）都可以这种方式连接到代码控制台和内核。
