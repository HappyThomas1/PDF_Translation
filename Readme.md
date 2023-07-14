# PDF Translator

PDF Translatorは、Adobe APIを使用してPDFファイルからテキストを抽出し、そのテキストをOpenAIのGPT-3モデルを用いて日本語に翻訳するプログラムです。このツールは特に医学論文の翻訳に適しています。

## Installation

1. このリポジトリをクローンする:

    ```
    git clone https://github.com/yourusername/PDF_Translator.git
    ```

2. 必要なライブラリをインストールする:

    ```
    pip install -r requirements.txt
    ```

3. [Adobe Document Services API](https://www.adobe.com/devnet-docs/dcsdk_io/servicesSDK/howtos/auth/credentials.html) と [OpenAI API](https://beta.openai.com/docs/developer-quickstart/) のAPIキーを取得し、環境変数に設定する:

    ```
    export PDF_SERVICES_CLIENT_ID=your_adobe_client_id
    export PDF_SERVICES_CLIENT_SECRET=your_adobe_client_secret
    export OPENAI_API_KEY=your_openai_key
    ```

## Usage

このアプリケーションは、GUIベースで操作します。プログラムを実行すると、PDFファイルをドラッグ＆ドロップできるウィンドウが表示されます。

```
python extract_txt_from_pdf_Drag_and_Drop.py
```

翻訳したいPDFファイルをウィンドウにドラッグ＆ドロップしてください。また、翻訳したいページ範囲を指定することもできます。ページ範囲は1から始まります。

翻訳が完了すると、翻訳結果は元のPDFファイルと同じディレクトリ内に新たに作成される`_output`フォルダ内の`translated_text.txt`ファイルに保存されます。

## Note

* PDFファイルからテキストの抽出はAdobe PDF Servicesを使用しています。
* テキストの翻訳はOpenAIのGPT-3を使用しています。
* PDFファイルのページ番号は1から始まります。
* 翻訳は行単位で行われ、各行の最大文字数は約2000文字となっています。この制限はOpenAI APIの制約によるものです。
* アプリケーションは、Adobe APIまたはOpenAI APIの利用料金が発生する可能性があるため、利用には注意が必要です。

## Contributing

バグの報告や機能のリクエストなど、お気軽にGitHubの[issues](https://github.com/HappyThomas1/PDF_Translation/issues)に投稿してください。

## License

このプロジェクトはMITライセンスの下でライセンスされています。詳細は[LICENSE](https://github.com/yourusername/PDF_Translator/blob/main/LICENSE)をご覧ください。
