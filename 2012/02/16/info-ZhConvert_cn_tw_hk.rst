public: yes
tags: [python, restructuredtext, 簡繁互轉, 翻譯]
summary: |
  翻譯、其工具，及簡繁互轉
.. vim:set shiftwidth=4 tabstop=4 expandtab textwidth=79:

翻譯、其工具，及簡繁互轉
===========================
.. 前言

這裡打一段前言。Blog的簡單介紹

* http://gerry.lamost.org/blog/?p=603
* http://blog.tenyi.com/2011/08/blog-post.html
* http://svn.wikimedia.org/svnroot/mediawiki/trunk/phase3/includes/ZhConversion.php
* http://qiangheng.openfoundry.org/

分段

* 翻譯是？
* 如何翻譯？
* 翻譯工具
* 簡繁互轉




.. <!-- more -->

Introduction
=============

翻譯是？
--------

以下參照  [1]_ ::

  翻譯，是指在準確通順的基礎上，把一種語言信息轉變成另一種語言信息的活動。
  了解來源語言文意後，用目標語言寫出能表達本來文意的文章。


要求::

 信，達，雅. 
 準確、通順、貼切
 人名和地名的翻譯應該名從主人。

方法::

 對於新接觸或不熟練的語言，機械翻譯的辭典法（即逐字翻譯）是翻譯方法的最根本，所以把欲翻譯的文字的字面意思表達出來，是商務翻譯中的重要應用，也是翻譯的最初通行方法。
 翻譯家思果指出，理想的譯法是這樣的：先把原文看懂，照原文譯出來，看看念不念得下去，試刪掉幾個不一定用得著的字，看看是否有損文義和文氣。如果有損，再補回來。試把不可少的字加進去，看看是否超出原文範圍，增減以後和原文再校對一次。有些地方是否譯錯，語氣的輕重是否恰如其分，原文的弦外之音譯文裡找不找得到？原文的意思要消化；譯文的文字要推敲。有經驗的譯者，可能一下筆就譯好了，不過還是要花更多時間來推敲疑問的遣詞造句。

科技

機器翻譯::

 所謂機器翻譯，是指利用電腦程式對譯入語文本進行分析，然後自動將譯入語翻譯為譯出語電腦輔助翻譯
 電腦輔助翻譯:是以電腦程式軟體輔助人工翻譯，協助譯者更快速地翻譯以及維持詞彙的一致性。

翻譯記憶庫（Translation Memory，簡稱 TM)::

 以資料庫的方式儲存原文與譯文(TRANSIT,OmegaT...)

電話翻譯::

 電話翻譯，顧名思義，是以現代通訊手段的電話或手機，進行實時的交傳或同傳，協助不同語種人員的語言交流和溝通。這是各國在努力發展的一項重要應用。

 
翻譯原則？
------------

翻譯的原則？如何翻譯呢？ 以下參考 [2]_

這節資料收集要點

* 以Wikipedia為主要參考的來源
* 預設為英翻中為主

i18n: internationalization 國際化，程式可以支援其他國語言, 用gettext的 _("xxx")
l10n: localization 本地化，翻譯介面成本地的語言，ex: zh_TW.po

翻譯要點

* 注意語言地區性、一字多義、歷史因素所可能產生的字詞多義
* 外語的漢字不適合直接留字,ex:渋谷区」⇒「澀谷區」
* 難譯外語留用原文: 外語人名、地名、影視作品、ACG作品等的譯名可能在各中文使用地區會在翻譯時有所不同，因此應考慮加上各地區譯名，以方便不同地區之閱讀者。 ex: 歐巴馬(Obama)
* 請以句子為單位翻譯: 如果遇到較難句子可暫時保留，待他人翻譯，最好不要按單詞翻譯，這樣可能斷開整句，給其他翻譯者理解上下文造成困難。若是科技文章，可以段落為單位翻譯，以保持原義為主。

翻譯資源


* 中華民國官方的國家譯名. 中華民國外交部 （正體中文）.
* `學術名詞資訊網. 國立編譯館 （正體中文) <http://terms.nict.gov.tw/>`_
* 《翻譯學研究集刊》參考書目. 台灣翻譯學學會 （正體中文）.
* 日本動漫（巴哈姆特）. 巴哈姆特電玩資訊站 （正體中文）.
* 本國專利技術名詞中英對照詞庫查詢系統
* 兩岸名詞對照查詢系統
* 海峽兩岸動物學名詞對照
* 中華語文知識庫（台灣版）


* `Wikipedia:術語表 <http://zh.wikipedia.org/wiki/Wikipedia:术语表>`_
* `Wikipedia:專用詞 <http://zh.wikipedia.org/wiki/Wikipedia:专用词汇翻译索引>`_ 
* `Wikipedia:科技條目翻譯指引 <http://zh.wikipedia.org/wiki/Wikipedia:科技条目翻译指引>`_

Jjhou

* 英中繁簡編程術語對照 (Terms) http://jjhou.boolan.com/terms.htm
* Jjhou的C++Primer翻譯方式: <技術引導乎 文化傳承乎by 候捷>
    * 保留許多專有關鍵字(keyword)不譯
    * 中英並列，頁頁對譯，保留原書索引


專有名詞翻譯

* 中文譯名，以Wikipedia為主，其次是其他的官方的譯名。
* 專有名詞是否翻譯，或者留用原文？ ex: string, template, framework, 參見 候捷 翻譯

翻譯工具
--------

格式

* GNU po:
* QT qm:
* tmx: 翻譯記憶庫，以文章為主

離線工具

OmegaT:
poEdit:
Lokalize:
gtranslator:
UbuntuTranslater:

線上翻譯網站

Transifex:
LaunchPad:
Pootle:
Tryneeds:
Google Translate:

軟體翻譯注意事項

* 自由軟體中文化工作指南
* <http://wiki.ubuntu-tw.org/index.php?title=%E8%87%AA%E7%94%B1%E8%BB%9F%E9%AB%94%E4%B8%AD%E6%96%87%E5%8C%96%E5%B7%A5%E4%BD%9C%E6%8C%87%E5%8D%97>`_
* `翻譯po檔注意事項 <http://kde.linux.org.tw/kde-i18n/trans-po.html>`_



簡繁互轉
--------

簡繁互轉

* 簡體字 <--> 繁體字
* 中國、香港、台灣、星馬用語不同，譯名不同
* 簡繁互轉不一定可逆,ex: 幹->干->干

維基百科
同文堂


繁簡翻譯小技巧 <http://www.ubuntu-tw.org/modules/newbb/viewtopic.php?viewmode=flat&type=&topic_id=20154&forum=15>

* http://zh.wikipedia.org/zh-tw/Wikipedia:字詞轉換處理/公共轉換組
* http://zh.wikipedia.org/wiki/Help:中文维基百科的繁简处理
* http://svn.wikimedia.org/viewvc/mediawiki/trunk/phase3/includes/ZhConversion.php
* http://zh.wikipedia.org/wiki/Wikipedia:简繁一多对应校验表
* http://zh.wikipedia.org/wiki/Wikipedia:繁简一多对应校验表




.. warning:: Warning
.. note:: Note
.. rubric:: Ruby是？


Reference
=========
.. 參考文件連結

.. [1] `Wikipedia:翻譯 <http://zh.wikipedia.org/wiki/翻译>`_
.. [2] `Wikipedia:翻译守则 <http://zh.wikipedia.org/wiki/Wikipedia:翻译守则>`_

.. 其他參考的連結，人，網站，wikipedia page

.. _Python: http://www.python.org

