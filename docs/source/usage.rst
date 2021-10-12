Usage
=====

.. _installation:

Installation
------------

To use Lumache, first install it using pip:

.. code-block:: console

   (.venv) $ pip install lumache

Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

Using Chinese
--------------
使用中文
rst
reStructuredText (reST) is the default plaintext markup language used by both Docutils and Sphinx. Docutils provides the basic reStructuredText syntax, while Sphinx extends this to support additional functionality.

sphix
Sphinx is a tool that makes it easy to create intelligent and beautiful documentation, written by Georg Brandl and licensed under the BSD license.

xetex
xetex – An extended variant of TeX for use with Unicode sources

luatex
LuaTeX is an extended version of pdfTeX using Lua as an embedded scripting language.

sphinx
~~~~~~~
使用中文

option 1:

sphix-quickstart时有
::
   Projetct language [en]:

默认是en, 选择zh, 这样编译成latex时会默认选择xetex.

option 2:

按照默认，但是在source/conf.py 添加
language = 'zh'
latex_engine = 'xelatex'

option 3:

按照默认，但是在source/conf.py 添加
language = 'zh'
latex_engine = 'luatex'

生成的xxx.tex文件修改一下
::

   -\usepackage{fontspec}
   +%\usepackage{fontspec}
   +\usepackage{luatexja-fontspec}
   +\setmainjfont{Noto Sans CJK SC}

生成pdf时latexmk, 默认用的是pdfLaTeX, 所以生成pdf会报错, 用texworks输出.

pandoc也是一个很好的工具。

Font
~~~~
字体
::

   fc-list | grep CJK
   fc-scan ~/.fonts/google-noto-cjk/NoteSansCJK-Regular.ttc | more

这样可以获得字体名称.

Texworks
~~~~~~~~~~
The TeXworks project is an effort to build a simple TeX front-end program (working environment) that will be available for all today's major desktop operating systems—in particular, MS Windows (7/8/8.1/10), typical GNU/Linux distros and other X11-based systems, as well as macOS. It is deliberately modeled on Dick Koch's award-winning TeXShop for Mac OS X, which is credited with a resurgence of TeX usage on the Mac platform.

还有更多的选择
* AUCTEX
* GNU TeXmacs
* lyx
* TeXstudio
* ...

安装可以用flatpak, 可以增量更新， 也可以用发行版打包的texlive，用包管理器安装.

Typeset 选择xelatex, 或者lualatex.
