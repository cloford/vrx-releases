# VRX

VRChatのフレンド状態を表示し、選んだフレンドのオンライン・オフラインをDiscordに通知するデスクトップアプリです。公式のQR承認画面を使い、VRXからDiscordの送信先チャンネルを選べます。VRChatおよびDiscordの非公式アプリです。

## ダウンロード

[最新版の配布ページ](https://github.com/cloford/vrx-releases/releases/latest) の **Assets** から、お使いのOSに合ったZIPを選びます。ダウンロードにGitHubアカウントは不要です。

| 対象 | ZIP | 起動方法 |
| --- | --- | --- |
| Windows x64 | `VRX-1.0.10-windows-x64.zip` | ZIP全体を展開し、`VRX/VRX.exe` を開きます。`_internal` は `VRX.exe` と同じフォルダに置きます。 |
| Mac（Appleシリコン） | `VRX-1.0.10-macos-arm64.zip` | ZIPを展開し、Finderで `VRX.app` を開きます。Pythonのインストールは不要です。 |

Mac版はアドホック署名です。Developer ID署名とAppleの公証は未実施です。信頼できる配布元から取得したこととSHA-256を確認したうえで、初回起動でブロックされた場合は、アプリを開こうとした直後に **システム設定 → プライバシーとセキュリティ → このまま開く** を選べます。管理されたMacでは利用できない場合があります。 [Appleの案内](https://support.apple.com/ja-jp/102445)

Windows版の `VRX.exe` はコード署名なしで、GitHub ActionsのWindows環境で起動を確認しました。Mac版はAppleシリコンのMacで起動を確認しました。

## 使い方

1. **Discordで送信先を選ぶ** を押し、ブラウザでチャンネルを選択します。
2. VRChat接続用の連絡先メールアドレスを入力して接続します。表示されたQRコードを読み取り、自分のアカウントで承認します。
3. 一覧で通知したいフレンドを選び、通知条件を設定します。フレンド詳細は行のダブルクリックで開けます。
4. **テスト通知** を送信し、Discordのチャンネルで投稿を確認します。iPhoneのプッシュ通知はDiscordとiOSの通知設定にも従います。

アプリを終了すると監視が止まります。再接続時にはQR承認が必要です。

## プレイ履歴

メイン画面の **プレイ履歴** を開くと、同じPCで収集したVRChatのログから、セッション、移動と滞在、同席、入室失敗を確認できます。プレイ履歴の閲覧にQR承認は不要です。フレンド詳細からは対象のフレンドIDで履歴を絞り込めます。

既定のログフォルダはWindowsでは `%USERPROFILE%/AppData/LocalLow/VRChat/VRChat`、Macでは `~/Library/Application Support/VRX/vrchat-logs` です。別の場所にあるログは **ログフォルダを選択** で指定できます。

## 更新と配布ファイル

旧版を終了し、公開リリースの新しいZIPを展開してアプリ一式を入れ替えてください。旧版のアプリ内更新確認は開発用リポジトリを参照するため、公開版は手動で更新してください。 [最新版の配布ページ](https://github.com/cloford/vrx-releases/releases/latest)

この配布用リポジトリのGit履歴には公開文書が含まれます。使うファイルは **Assets** にあるOS別ZIPです。GitHubが自動生成する **Source code** は配布用リポジトリの文書アーカイブです。

実行ファイルにはコンパイル済みのPythonバイトコードが含まれます。解析・抽出によって実装を再構成できる場合があります。第三者ソフトウェアのライセンス文書はリリースの `VRX-1.0.10-third-party-notices.zip` およびMac用ZIP内で確認できます。
