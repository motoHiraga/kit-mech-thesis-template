# 【非公式｜工繊大・機械】卒論・修論 LaTeX テンプレート

京都工芸繊維大学 機械工学課程／機械物理学専攻・機械設計学専攻の卒業論文・修士論文用のテンプレートです．

執筆要綱などについては大学のWebページを参照：
[卒業論文・修士論文 - 京都工芸繊維大学 機械工学課程](http://www.mech.kit.ac.jp/student/thesis.html)

## コンパイラの変更方法
``thesis_main.tex``から``kit_mech_thesis``のオプションを書き換えてください．
- pLaTeXの場合：
  ``\documentclass[platex,dvipdfmx]{kit_mech_thesis}``
- upLaTeXの場合：
  ``\documentclass[uplatex,dvipdfmx]{kit_mech_thesis}``
- LuaLaTeXの場合：
  ``\documentclass[lualatex]{kit_mech_thesis}``

## 【おまけ】多分一番早い VS Code での LaTeX 環境構築方法

1. VS Code の拡張機能 LaTeX Workshop をインストールする．
2. ``latexmkrc`` を用意する． 
3. ``thesis_main.tex``と同じ場所に``latexmkrc``を保存する．
4. LaTeX Workshop の設定にて，Default（Latex-workshop > Latex > Recipe: Default）を「first」から「latexmk (latexmkrc)」に変更する．

<details><summary>latexmkrc の例（upLaTeX + upBibTeX の場合）</summary>

```
$latex = 'uplatex -synctex=1 -file-line-error -halt-on-error %O %S';
$bibtex = 'upbibtex %O %B';
$dvipdf = 'dvipdfmx %O -o %D %S';
$pdf_mode = 3;
```
