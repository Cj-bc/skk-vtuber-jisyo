[English](README.md)

---

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
[dicts/](dicts/)以下の各ファイルについて。

- make targetが存在するか
- 'all' targetにそのファイルのmake targetが依存ファイルとして指定されているか

をテストします。

# 使用上の注意

必ず __ハードリンク__ してください。
シンボリックリンクはうまく動かないようです。

# Contributing

自由にPR/issueしてください。
