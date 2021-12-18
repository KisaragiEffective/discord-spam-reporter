# discord-spam-reporter
![Build](https://img.shields.io/github/workflow/status/yanorei32/discord-spam-reporter/CI?logo=github&style=for-the-badge)
![License](https://img.shields.io/github/license/yanorei32/discord-spam-reporter.svg?style=for-the-badge&color=blue)
![Top Language](https://img.shields.io/github/languages/top/yanorei32/discord-spam-reporter.svg?style=for-the-badge)

## 導入
(※DiscordのBotトークンが必要です)

1. `cargo build --release`
2. `target/release/discord-spam-reporter` を取り出す
3. `config.yml` を作成する
4. `config.yml` を以下の内容で作成する (内容は適宜書き換える)
```yml
# 通知するチャンネルのID
report_channel: 987654323109876543
# 通知するサーバーのID
guild: 918273645647382910
# Botのトークン
token: "Your token here"
# patternには正規表現を指定する。
# 正規表現の書式は https://docs.rs/regex/1.5.4/regex/#syntax を参照。
rules:
  - pattern: ".+"
    note: "何らかのメッセージ"
  - pattern: "free +nitro"
    note: "free nitroを検知"
```

5. 環境変数`CONFIG`に`config.yml`の存在する場所をフルパスまたはワーキングディレクトリからの相対パスで指定する<br>\(例 `/home/kisaragi/projects/discord-spam-reporter/config.yml`, `./config.yml`\)