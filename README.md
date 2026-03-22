# Qiita CLI

- [📘 How to use](https://qiita.com/Qiita/items/666e190490d0af90a92b)

## 基本的な手順

- 記事の作成

  ```bash
  npx qiita new 記事のファイルのベース名
  ```

- プレビュー

  ```bash
  npx qiita preview
  ```

  デフォルトURL http://localhost:8888

- 公開  
  ファイルをコミットし、Qiita と連携されている GitHub リポジトリにプッシュ
  - 手動で公開
    ```bash
    npx qiita publish 記事のファイルのベース名
    ```

## 導入手順

- フォルダ構成

  ```
  articles/
  ├─ .devcontainer/
  │    └─ devcontainer.json  # コンテナ設定ファイル
  ├─ zenn-contents/          # Zenn記事用ディレクトリ (Gitリポジトリ)
  └─ qiita-contents/         # Qiita記事用ディレクトリ (Gitリポジトリ)
  ```

- `devcontainer.json`
  ファイルを作成して `articles/` をVSCodeで開き，必要なパッケージ（`Dev Containers`）をインストールすれば完了．

  ```json
  {
    "name": "Zenn & Qiita Writing Env",
    "image": "mcr.microsoft.com/devcontainers/javascript-node:24",
    "customizations": {
      "vscode": {
        "settings": {
          "terminal.integrated.defaultProfile.linux": "bash"
        },
        "extensions": [
          "ms-vscode.live-server",
          "esbenp.prettier-vscode",
          "donjayamanne.githistory"
        ]
      }
    }
  }
  ```

- `qiita-contents/` 内
  1.  新規作成する場合

  ```bash
  cd qiita-contents
  npm init --yes
  npm install @qiita/qiita-cli --save-dev
  npx qiita init
  ```

  2.  GitHubからインストールした場合

  ```bash
  cd qiita-contents
  npm install
  ```

## ヘルプ

- VSCodeを開いてもDockerが起動しない
  1. F1 キー
  2. `reopen` と入力し，「Dev Containers: Reopen in Container (コンテナーで再度開く)」を選択
