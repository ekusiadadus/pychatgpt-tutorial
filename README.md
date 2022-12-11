## 追記(2022.12.12)

この記事は、Qiita のアドベントカレンダー 2022 に投稿された内容です。
要望があったので、GitHub にコードを載せたものを公開します。

## 動かし方

`main.py` の　`email` と `password` に、OpenAI のアカウントのメールアドレスとパスワードを入れてください。

[poetry](https://github.com/python-poetry/poetry) をインストールして、以下のコマンドを実行してください。

```bash
pip3 install poetry
poetry install
poetry run python main.py
```

# 今話題の ChatGPT を Python でいい感じに使ってみよう！

すでにご存知の方も多いと思いますが、ChatGPT は一世を風靡している強力な自然言語処理（NLP）ツールです。人間のようなテキストの生成から、チャットボットやバーチャルアシスタントの構築まで、幅広い用途で利用されています。

ChatGPT の人気の理由の 1 つは、大量のテキストデータで学習させた強力なオープンソースの GPT-3 言語モデルの上に構築されていることです。これにより、ChatGPT は非常に現実的で一貫性のあるテキストを生成することができ、NLP に携わる人にとって貴重なツールとなっています。

しかし、ChatGPT が本当に特別なのは、世界で最も人気のあるプログラミング言語の 1 つである Python で使用するように設計されていることです。Python の基本的な知識があれば、誰でも簡単に ChatGPT をプロジェクトに組み込んで、その強力な機能を使い始めることができるのです。

この記事では、ChatGPT の詳細と、Python でどのように使用できるかを見ていきます。また、ChatGPT の潜在的なアプリケーションのいくつかと、それがどのように良い方向に使われるのかについて説明します。

(ここまで ChatGPT 君)

ChatGPT すごいですよね...
GitHub 見ると最近の Star 数が多くついているのは ChatGPT 関連です。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/8dae9c65-feac-af88-a8c2-cacaff0887a6.png)

ということで ChatGPT の Python パッケージ [PyChatGpt](https://github.com/rawandahmad698/PyChatGPT) を触ってみました！

https://github.com/rawandahmad698/PyChatGPT

## インストール

```
pip install chatgptpy --upgrade
```

いろんなパッケージがあるのですが、一番使いやすいと思います。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/0c1e6960-8a1b-cf0a-c036-01912b074bfe.png)

## 使ってみる

インストール成功したら、`chat.py` ファイルを作って実際に使ってみましょう。

```python:chat.py
from pychatgpt import Chat, Options

options = Options()

options.track = True

options.chat_log = "chat_log.txt"
options.id_log = "id_log.txt"

chat = Chat(email="email", password="password", options=options)
chat.cli_chat()
```

`email` と `password` は [OpenAI](https://beta.openai.com/login/) のアカウントを作成して、そのアカウントのメールアドレスとパスワードを入れてください。

```
python3 chat.py
```

だけで疑似 ChatGPT CLI ツールが体験できます！

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/de27586c-8955-cd52-3b0a-efd8ad6f9bfc.png)

```
You: おはよ！
Chat GPT: こんにちは！ 私は Assistant です。どういたしまして？
You: Qiitaのアドベントカレンダー書かないといけなくて憂鬱なんだよね...
Chat GPT: 「Qiita のアドベントカレンダー」とは何でしょうか？ 私は知りません。ご存知の方がいらっしゃいましたら、是非ご教授ください。


You: [A[A[B
Chat GPT: [Status Code] 403 | [Response Text] <!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'><head><meta content='text/html; charset=utf-8' http-equiv='content-type'/><style type='text/css'>body { font-family:Arial; margin-left:40px; }img  { border:0 none; }#content { margin-left: auto; margin-right: auto }#message h2 { font-size: 20px; font-weight: normal; color: #000000; margin: 34px 0px 0px 0px }#message p  { font-size: 13px; color: #000000; margin: 7px 0px 0px 0px }#errorref { font-size: 11px; color: #737373; margin-top: 41px }</style><title>Microsoft</title></head><body><div id='content'><div id='message'><h2>The request is blocked.</h2></div><div id='errorref'><span>0ZlSTYwAAAAAVbBAdZOMlRrC59NnC25S0VFlCRURHRTA3MTAAZTY2YjhiMDMtMDc5My00NDA5LTk3NzMtMmU2MTJlNzFhMWUz</span></div></div></body></html>
You: 12月にIT関連の記事を書くイベントのことなんだけど、時間があんまりなくてさ...
Chat GPT: それは大変そうですね。12月にIT関連の記事を書くイベントは、時間が限られているようです。そのような状況では、まずは何を書くかを明確にすることが重要です。そして、時間を効率よく使うために、記事の執筆にかかる時間を正確に見積もることも大切です。また、他の参加者やイベントのオーガナイザーと協力し合い、タスクを分担することも検討してみると良いでしょう。
You: 励まして！
Chat GPT: いえいえ、それは大丈夫です。そういう時には、まずは自分自身に自信を持つことが大切です。自分ができることを確認し、自分にとって可能な範囲で最善を尽くすことが大切です。そして、自分が書く記事がどのようなものであるかを心に留めておくことも大切です。そうすれば、書くことを楽しむことができるでしょう。最後に、自分の努力が報われるよう祈っています。頑張ってください！

```

```
You: ChatGPT を Python で使ってみる記事を書いて！
Chat GPT:
[省略]
今回は、ChatGPTの詳細と、Pythonでどのように使用できるかを見ていきます。
また、ChatGPTの潜在的なアプリケーションと、それがどのように良い方向に使われるのかについて説明します。

まず、ChatGPTがどのように機能するかについて説明します。ChatGPTは機械学習モデルであり、与えられた入力に基づいてテキストを生成するように訓練されています。
この入力は、単一の単語、文章、または段落全体であることができ、ChatGPTは入力に関連する応答を生成します。

ChatGPTの大きな特徴の一つは、人間のようなテキストを生成する能力です。
これは、膨大なテキストデータで学習させたGPT-3言語モデルを用いているためです。
これにより、ChatGPTは適切な応答だけでなく、非常に首尾一貫した自然な響きを持つ応答を生成することができます。

PythonでChatGPTを使用することは非常に簡単です。
Python Package Index (PyPI)で公開されているChatGPT Pythonパッケージをインストールすればよいだけです。
パッケージのインストールが完了したら、ChatGPTクラスをインポートし、クラスのインスタンスを作成することで、PythonコードでChatGPTを使用することができます。

以下は、PythonでChatGPTを使用する例です。
```

うん。めちゃくちゃにすごい。

だけど、ブラウザじゃないから最後のサンプルコードが見れないのが残念。
他にも面白いツールがあったので、ご紹介します。

## ChatGPT 関連ツール

ここからは、ChatGPT 関連のツールを紹介します。
正直、よさげなツールは少ないです。
でも開発の黎明期とはこういう感じなんだというのをひしひしと感じます。
いろんな人が、いろんなアイデアをもとに自分の得意なソフトウェア開発を行っているので、是非ともチェックしてみてください。

### CLI ツール

#### auto-commit (★★★★☆)

https://github.com/m1guelpf/auto-commit

おすすめ度: ★★★★☆

[auto-commit](https://github.com/m1guelpf/auto-commit) は、コードの差分を読み取って自動的にコミットメッセージを書いてくれる CLI ツールです。

```
auto-commit
```

これだけ。差分とかから、自動的にコミットメッセージを作ってくれます。
ただ、コミットメッセージは英語です...
あと conventional commit を守ってくれるときと、守ってくれないことがあるので、その辺は注意が必要です。
★4 つです。

![auto-commit.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/1a7a8eac-77f1-29b6-2831-735aef86d5d3.gif)

### Python ライブラリ

#### PyChatGPT (★★★★☆)

https://github.com/rawandahmad698/PyChatGPT

おすすめ度: ★★★★☆

上でも紹介したパッケージ。
個人的に、好き。
ただ、日本語だとちょっと使いづらいかもしれない。

#### ChatGPT (★★★☆☆)

https://github.com/acheong08/ChatGPT

おすすめ度: ★★★☆☆

[ChatGPT](https://github.com/acheong08/ChatGPT) は、ChatGPT を Python で使えるようにしたライブラリです。
[PyChatGpt](https://github.com/rawandahmad698/PyChatGPT) と似ています。
個人的には、[PyChatGpt](https://github.com/rawandahmad698/PyChatGPT)の方が使いやすいと思っているので、★3 つです。

### Node.js ライブラリ

#### chatgpt-api (★★★☆☆)

https://github.com/transitive-bullshit/chatgpt-api

おすすめ度: ★★★☆☆

[chatgpt-api](https://github.com/transitive-bullshit/chatgpt-api) は、ChatGPT の Node.js ライブラリ です。

![demo.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/051e02e5-e151-0e90-67c5-be5c423e6c46.gif)

### Dart ライブラリ

#### chatgpt_api_dart (★★★☆☆)

https://github.com/MisterJimson/chatgpt_api_dart

おすすめ度: ★★★☆☆

[chatg_api_dart](https://github.com/MisterJimson/chatgpt_api_dart) は、ChatGPT の Dart ライブラリ です。

### VSCode 拡張機能

#### chatgpt-vscode (★☆☆☆☆)

https://github.com/mpociot/chatgpt-vscode

おすすめ度: ★☆☆☆☆

[chatgpt-vscode](https://github.com/mpociot/chatgpt-vscode) は、ChatGPT を VSCode で使えるようにしたものです。
正直、あんまり...

### Chrome 拡張機能

#### chat-gpt-google-extension (★★☆☆☆)

https://github.com/wong2/chat-gpt-google-extension

おすすめ度: ★★☆☆☆

[chat-gpt-google-extension](https://github.com/wong2/chat-gpt-google-extension) は、ChatGPT を Chrome Extension で使えるようにしたものです。

### SNS ボット系

#### wathsapp-gpt (★★☆☆☆)

https://github.com/danielgross/whatsapp-gpt

おすすめ度: ★★☆☆☆

[wathsapp-gpt](https://github.com/danielgross/whatsapp-gpt) は、ChatGPT を WhatsApp で使えるようにしたものです。

Go 言語で書かれています。

#### chatgpt-twitter-bot (★★★☆☆)

https://github.com/transitive-bullshit/chatgpt-twitter-bot

おすすめ度: ★★★☆☆

[chatgpt-twitter-bot](https://github.com/transitive-bullshit/chatgpt-twitter-bot) は、ChatGPT を Twitter Bot で使えるようにしたものです。
普通に陰キャ ツイッタラー には向いていると思います。

#### chatgpt-telegram-bot (★★☆☆☆)

[chatgpt-telegram-bot](https://github.com/franalgaba/chatgpt-telegram-bot-serverless) は、ChatGPT を Telegram Bot で使えるようにしたものです。

おすすめ度: ★★☆☆☆

![chatgpt_animation_fast.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/7d26b93a-0730-f0fd-03c0-cad108697a4a.gif)

### Excel, Google Docs など

#### docGPT (★★☆☆☆)

https://github.com/cesarhuret/docGPT

おすすめ度: ★★☆☆☆

[docGPT](https://github.com/cesarhuret/docGPT) は、ChatGPT を Google Docs で使えるようにしたものです。
一応、Excel からでも ChatGPT 呼べるように作ってあるらしい。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/45cb6344-c090-d814-782b-dc19065343f9.png)

### GitHub Actions

#### chatgpt-action (★★☆☆☆)

https://github.com/kxxt/chatgpt-action

おすすめ度: ★★☆☆☆

[chatgpt-action](https://github.com/kxxt/chatgpt-action) は、ChatGPT を GitHub Actions で使えるようにしたものです。

正直わかりづらい...

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/905557/05b70879-6d7a-3abd-a27e-75a57f41e466.png)

```
This pull request introduces several syntax errors.
In the diff, on line 6, the const keyword should be replaced with import in ...
```

上みたいにレビューしてくれるのですが、ちょっとわかりづらい...
でも将来性はありそう。
AWS Guru とかでも自動レビューは既に存在していますし

### 話す系

#### chatgpt-conversation (★★☆☆☆)

https://github.com/platelminto/chatgpt-conversation

おすすめ度: ★★☆☆☆

[chatgpt-conversation](https://github.com/platelminto/chatgpt-conversation) は、話す感覚で使えるようにしたものです。

この手のやつ、`stable Diffusion` とか出てきたとき `whisper` と組み合わせてみました！みたいな感じでたくさんあります。。。

### デスクトップアプリ系

#### ChatGPT を tauri でデスクトップアプリ化したもの (草)

https://github.com/lencx/ChatGPT

おすすめ度: ★☆☆☆☆

[ChatGPT を tauri でデスクトップアプリ化したもの](https://github.com/lencx/ChatGPT) は、ChatGPT をデスクトップアプリ化したものです。

ここら辺になると、もう草という感じですね...
ChatGPT 関係ないじゃん...

### まとめ系

#### awesome (★★★★★)

https://github.com/humanloop/awesome-chatgpt

おすすめ度: ★★★★★

[awesome](https://github.com/humanloop/awesome-chatgpt) は、ChatGPT に関するリポジトリのリストです。

最近、ChatGPT に関するリポジトリが増えてきているので、まとめてくれています。

https://github.com/f/awesome-chatgpt-prompts

[awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) みたいなのもあって、ChatGPT にどのようにふるまって欲しいかの cook book みたいなのもあります。

## ChatGPT 関連コミュニティ

### Discord

https://discord.com/invite/openai

[Discord](https://discord.com/invite/openai) には、ChatGPT のコミュニティがあります。

## まとめ

以前、PODCAST で Google や OpenAI などの AI 企業のエンジニアが話していたのですが、数年後には Google や OpenAI がチューニングしなくても、自分でチューニングできるようになると言っていました。
そうなるといよいよ AI が人間を超える時代が来るのかもしれません。

自分は 5 年後には自分の仕事がなくなればいいのになと思っています。
