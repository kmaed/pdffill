pdffill パッケージ
=================

概要
----

申請書や報告書といった事務書類を作成するとき，慣れない Word や Excel の様式を送ら
れて編集する必要に迫られることが多いです．特にある程度の長さの文章を記述する欄があ
る場合，Word や Excel では無様な仕上がりになってしまったり，枠が崩れてしまったり，
ページ数が不意に増えたりしてイライラします（使い方が下手なせいかもしれないが）．
あげくの果てに保存したファイルを開こうとしたらクラッシュした日には……（←実体験）．

pdffill は使い慣れた LaTeX で美しく事務書類を作成するためのパッケージです．目標は
[科研費 LaTeX](http://osksn2.hep.sci.osaka-u.ac.jp/~taku/kakenhiLaTeX/)の方法
を一般化することです．

必要環境
--------

PDF を扱える e-TeX エンジンと，そのエンジンの LaTeX フォーマットの実行形式が必要
です．すなわち pdflatex, xelatex, lualatex のいずれかが必要です．特に日本語を扱
いたい場合は pdflatex ではほぼ無理なので，xelatex か lualatex のどちらかが必要
となります．

また，以下の LaTeX パッケージが必要です．

 * [pdfpages](http://www.ctan.org/tex-archive/macros/latex/contrib/pdfpages)
 * [pgf](http://www.ctan.org/tex-archive/graphics/pgf)
 * [expl3](http://www.ctan.org/tex-archive/macros/latex/contrib/expl3)
 * [xparse](http://www.ctan.org/tex-archive/macros/latex/contrib/xpackages)
 * 日本語を適切に扱うためのパッケージ（使い方はそれぞれのパッケージの説明を参照）

    * xelatex の場合: [zxjatype](http://zrbabbler.sp.land.to/zxjatype.html)
    * lualatex の場合: とりあえず [luajalayout](http://www-is.amp.i.kyoto-u.ac.jp/lab/kmaeda/lualatex/luajalayout/)  
                       そのうち [luatexja](http://sourceforge.jp/projects/luatex-ja/wiki/FrontPage)

使い方
------

pdffill.pdf を参照（これから作成予定）．

機能の概要
---------

基本的には，pdfpages で PDF ファイルを取り込んで，その上に PGF/TikZ で書こうとい
う発想です．ただ，これだけだと大変なので，記入を支援するための機能がついています．

 * グリッドを描く: grid オプションを指定すると取り込んだ PDF の上に方眼が描かれま
                  す．これを見ながら記入する位置を指定することができます．
 * 記入したテキストの枠を表示: draft オプション．
 * 細かい枠への対応: よくある一文字ずつ記入するやつです．\splitboxes を使います．

なお，記入したいファイルが Word などの形式の場合，一度 PDF に変換する必要があり
ます．適当な方法で対処して下さい．

ToDo
----

 * 複数ページにまたがるテキスト枠への対応．

意見・要望など
-------------

前田一貴 (kmaeda at users.sourceforge.jp) までお願いします．GitHub 経由でも構い 
ません．
