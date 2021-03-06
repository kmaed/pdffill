pdffill パッケージ for LaTeX
============================

概要
----

申請書や報告書といった事務書類を作成するとき，慣れない Word や Excel の様式を送られて編集する必要に迫られることが多いです．特にある程度の長さの文章を記述する欄がある場合，Word や Excel では無様な仕上がりになってしまったり，枠が崩れてしまったり，ページ数が不意に増えたりしてイライラします（使い方が下手なせいかもしれないが）．あげくの果てに記入して保存したファイルを修正のためにもう一度開こうとしたらクラッシュした日には……（←実体験）．

pdffill は使い慣れた LaTeX で美しく事務書類を作成するためのパッケージです．目標は[科研費 LaTeX](http://osksn2.hep.sci.osaka-u.ac.jp/~taku/kakenhiLaTeX/) の方法を一般化することです．

注意
----

このパッケージを使えるのは，印刷した紙媒体のみを提出すればよい場合です．記入した Word や Excel のファイルが求められていて，提出後に相手方が変更を加える場合には使えません．後者の場合はこのパッケージで頑張って記入しても無駄になってしまうので，使用前に大丈夫かどうかよく考えましょう．

必要環境
--------

PDF を扱える e-TeX エンジンと，そのエンジンの LaTeX フォーマットの実行形式が必要です．すなわち pdflatex, xelatex, lualatex のいずれかが必要です．以前は (u)platex では使えませんでしたが，[2015年7月以降は pdfpages が dvipdfmx に対応したため](http://oku.edu.mie-u.ac.jp/tex/mod/forum/discuss.php?d=1630)，利用可能です．

また，以下の LaTeX パッケージが必要です．

 * [pdfpages](http://www.ctan.org/tex-archive/macros/latex/contrib/pdfpages)
 * [pgf](http://www.ctan.org/tex-archive/graphics/pgf)
 * [expl3](http://www.ctan.org/tex-archive/macros/latex/contrib/expl3)
 * [xparse](http://www.ctan.org/tex-archive/macros/latex/contrib/xpackages)
 * 日本語を適切に扱うためのパッケージ（使い方はそれぞれのパッケージの説明を参照）

    * xelatex の場合: [zxjatype](http://zrbabbler.sp.land.to/zxjatype.html)
    * lualatex の場合: [luatexja](http://sourceforge.jp/projects/luatex-ja/wiki/FrontPage)

使い方
------

[pdffill.pdf](https://github.com/kmaed/pdffill/blob/master/pdffill.pdf?raw=true) を参照．

機能
----

基本的には，pdfpages で PDF ファイルを取り込んで，その上に PGF/TikZ で書こうという発想です．ただ，これだけだと大変なので，記入を支援するための機能がついています．

 * グリッドを描く: grid オプションを指定すると取り込んだ PDF の上に方眼が描かれます．これを見ながら記入する位置を指定することができます．
 * 記入したテキストの枠を表示: draft オプション．
 * 細かい枠への対応: よくある一文字ずつ記入するやつです．\\splitboxes を使います．

なお，記入したいファイルが Word などの形式の場合，一度 PDF に変換する必要があります．適当な方法で対処して下さい．

ToDo
----

 * 複数ページにまたがるテキスト枠への対応．

意見・要望など
-------------

前田一貴 (kmaeda at kmaeda.net) までお願いします．GitHub 経由でも構いません．
