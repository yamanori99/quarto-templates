# テンプレートの使い方  
**日付**: 2024/09/22

## 概要
このテンプレートは、**Quarto**を使用して文書を作成するためのものです。以下の手順に従って、設定を行ってください。

## 使用条件
- Quartoがインストールされた環境が必要です。
- 使用するIDEは問いませんが、私は**Positron**を使っています。

参考リンク: [Quartoの基本的な使い方](https://www.jaysong.net/RBook/quarto1.html)（RStudioでの扱いを前提としています）。

## ファイルの構成
- **HTMLファイル**と**template_files**フォルダはサンプルですので、削除しても問題ありません。
- メインの`.qmd`ファイルと同じフォルダに**YAMLファイル**を配置し、以下のようなメタ情報を記入します：
  - 文書のタイトル
  - 作成者
  - 作成日
  - 出力フォーマット（HTML、PDF、Microsoft Wordなど）

## 出力設定
テンプレートには、以下の出力形式があらかじめ設定されています：
- HTML
- PDF
- reveal.js（HTMLで出力されるスライド）

普段追加しそうなオプション以外は`#`でコメントアウトされていますので、必要に応じて編集してください。  
なお、スライドのPDF出力は推奨されていません。PDFが必要な場合は、ブラウザーで表示したスライドのHTMLページをPDFとして書き出すのが簡単です。

## 注意点
- HTMLファイルを共有する際は、必ずフォルダごと丸ごと共有する必要があります（テンプレート内の「template_files」フォルダも含めて）。
- PDFレンダリングにはTeX環境が必要です。RStudioやPositronのコンソールで以下のコマンドを実行してください：

    ```r
    install.packages("tinytex") # Quarto使用のための軽量TeXパッケージ
    tinytex::install_tinytex() # 'N'を選択
    # 参考: https://www.jaysong.net/RBook/quarto2.html#出力フォーマット

    tinytex::tlmgr_install("haranoaji") # 日本語PDF作成用、文字化け回避
    # lang: jaは指定しないでください
    # 参考: https://www.jaysong.net/RBook/quarto2.html#日本語が含まれたpdf
    ```

## 参考文献の管理
- `references.bib`（ファイル名は任意）に参考文献情報を追加することで、簡単に参考文献欄を作成できます。HTMLではポップアップ表示も可能です。
- APA 7thスタイルに準拠するために、`apa7.csl`というCSLスタイルファイルを用意し、YAMLで指定しています（Zotero提供）。

## その他注意点
- APA 7thのスタイルは、日本語対応が不十分です。（だれか心理学研究の手引に合わせたスタイルを作っていないかな…）
- テンプレートは作りたてなので、不具合があるかもしれません。ご了承ください。（無責任）

## 追加リソース
- [Quartoによる引用可能な記事の作成方法](https://quarto.org/docs/authoring/create-citeable-articles.html)
