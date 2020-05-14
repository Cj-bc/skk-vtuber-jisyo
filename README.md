![test runner](https://github.com/Cj-bc/skk-vtuber-jisyo/workflows/test%20runner/badge.svg?branch=master)

# VTuber用SKK辞書

VTuber関連の単語を集めたSKK辞書です。
UTF-8です。


# 使い方

このレポジトリはVTuberを箱(所属事務所/企業/グループなど)毎にファイルを分けてあります。
自分の必要なもののみを組み合わせて辞書を作ることができるようになっています。

## 全ての辞書を含めて生成する

全ての辞書を含めるには、`make all`を実行します。

```sh
$ make all
# dist/vtuber.dict が生成されます。

$ make # 単体でも可
```

## 辞書を指定して生成する

辞書を指定するには、その辞書のファイル名から`.vtuber.dict`を取り除いたものを渡します。

```sh
$ make hololive
# ホロライブのみの辞書を生成

$ make kamitsubaki avatar20project
# 神椿スタジオとAvatar 2.0 Projectのみの辞書を生成
```

## 指定できる辞書の一覧を表示する

```sh
$ make list
```

## テストを走らせる

Makefileが正しく設定されているかのテストを走らせます。
[dicts/](dicts/)以下の各ファイルについて:

- make targetが存在するか
- 'all' targetにそのファイルのmake targetが依存ファイルとして指定されているか

をテストします。

# 使用上の注意

必ず __ハードリンク__ してください。
シンボリックリンクはうまく動かないようです。

# Contributing

## 既存のファイルへの変更/既にファイルのある箱に追加する

自由にPR/issueしてください。

## まだない箱を追加する

まず、まだその箱のファイルが存在しないか確認してください。
__個人勢は[kojin.vtuber.dict](dicts/kojin.vtuber.dict)に纏められている__ ので注意してください。
存在しなかった場合、以下の手順を踏んでください。

1. [dicts/](dicts/)以下に、 `<箱名>.vtuber.dict` の形式でファイルを作成し、書き込みます。
2. `make add T=<箱名>` で[Makefile](Makefile)の更新をします。これにより、そのファイルを指定してMakeできるようになります。

