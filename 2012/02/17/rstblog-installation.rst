public: yes
tags: [python, restructuredtext, rstblog]
summary: |
  rstblog是Armin Ronacher所寫的靜態html產生網站。這邊簡單敍述
  安裝，使用方式

rstblog 安裝，使用
===========================================

簡介
----

Armin Ronacher [1]_ 是 Flask_ , Jinja2_ ,...的作者。

rstblog是作者自已的blog的程式，用docutils把rst轉成靜態的網頁
，再同步到Github.com，或是其他web server。

同類的程式還有不少
Ruby: Jekyll_ , Octpress_ , Gollum_ (wiki) 
Python: Pelican_ , Hyde_ , Sphinx_ (documentation)

安裝
---

以下的安裝過程，參照 [2]_

假設你的blog的原始rst檔要放在 myblog::

 mkdir -p /path/to/myblog



rstblog沒在到PyPi上，所以只能從source安裝，
從github.com下載source::

  $git clone https://github.com/mitsuhiko/rstblog.git
  $cd rstblog
  $python setup.py install

Source中的 templates要複製到你的blog資料中::

  $cp -r rstblog/rstblog/templates /path/to/myblog/_templates

回到 myblog，並建設你的設定檔 config.yml::

  $cd /path/to/myblog
  $vim config.yml

config.yml的內容::

  ---
  active_modules: [pygments, tags, blog, latex, moudles_you_want_to_install]
  author: Your name
  canonical_url: http://myblog.github.com/
  modules:
    pygments:
      style: tango

建立放靜態檔css,image,js的資料匣  static/::

  $mkdir -p static/css
  $mkdir -p static/image
  $mkdir -p static/js

建立放blog post的rst檔的資料匣，是以年/月/日 來代表::

  $mkdir -p 2012/02/17
  $vim 2012/02/17/start_rstblog.rst

每個blog post的rst檔要加上特別的檔頭，以便程式讀取，
其中public指要不要公開blog post

start_rstblog.rst::

  public: yes
  tags: [python, restructuredtext]
  summary: |
    reStructuredText 產生靜態HTML檔_

  這一行是主要的標題Title，一定要有
  =============================================

  下面的內容就是一般的rst

Templates是使用 Jinja2_ ，程式中沒有附的是 _templates/layout.html
這邊參考 Armin Ronacher的網站的版本,再加以修改。
`layout.html <https://raw.github.com/mitsuhiko/lucumr/master/_templates/layout.html>`_

Makefiel，把一些指令整合到make中，就不必一直重復輸入::

  all: build
  
  clean:
      rm -rf _build
  
  build:
      run-rstblog build
  
  serve:
      run-rstblog serve

ok，接下來 開始來看看到目前為止的成果::

  $make build
  $make serve

就可以打開瀏覽器看看  http:://127.0.0.1:5000


目錄結構::

  myblog/
    2011/           blog post 的目錄
    _build/         run-rstblog執行完後，產生的靜態檔目錄
    _templates/     模版
    static/         靜態檔
    .gitignore      ignore git 不要同步的檔案 
    Makefile        自動化 
    about.rst       個人專頁
    config.yml      設定檔 

使用
----

pygments，原始碼syntax hightlighting::

  .. sourcecode:: javascript
  .. code-block:: python

latex.math，使用latex的數學符號::
  
  .. math::

其他想自己附加的功能可以用 doctuils的directive的功能，
寫法可以參照  rstblog/moudles/下的檔案，寫完後，記得
加入 config.yml

Web host
---------

目前網路上免費可以用Web host也不少，blog寫完了以後，
可以放到哪呢？

* `Github Pages`_ ，github應該是目前最熱門的社交原始碼交換社群(這樣翻？)
它也提供了可以存放網頁的服務， `Github Pages`_ 
* `Dropbox`_

另一種方式應該就是把rstblog修改，產生可以讓blogger,wordpress用的html，
用xmlrpc api上傳，不過這個方式的，可能需要較多的改動，可以參考 Doug Hellmann 
的 `rst2blogger <https://github.com/dhellmann/rst2blogger>`_


後記
----

其實目前靜態網頁產生程式還滿多的，原始檔主要就是rst,markdown這兩種系統。
有空也可以試試其他幾種。有空再來試試Pelican_, Hyde_。

References¬
==============

.. 參考文件連結¬
¬
.. [1] `Armin Ronacher的blog <http://lucumr.pocoo.org/>`_
.. [2] `heavenshell(日) rstblg安裝 <http://heavenshell.github.com/2012/01/28/start_rstblog/>`_
¬
.. 其他參考的連結，人，網站，wikipedia page¬
¬
.. _Python: http://www.python.org
.. _Flask: http://flask.pocoo.org/
.. _Jinja2: http://jinja.pocoo.org/¬
.. _Jekyll: https://github.com/mojombo/jekyll
.. _Gollum: https://github.com/github/gollum
.. _Octpress: http://octopress.org/
.. _Pelican: https://github.com/ametaireau/pelican
.. _Sphinx: http://sphinx-users.jp/
.. _Hyde: https://github.com/lakshmivyas/hyde
.. _`Github Pages`: http://pages.github.com/
.. _Dropbox: http://www.dropbox.com

¬
.. _thisfile:¬
.. vim:set shiftwidth=4 tabstop=4 expandtab textwidth=79:¬
.. template_version=0.3_20120112¬
 






