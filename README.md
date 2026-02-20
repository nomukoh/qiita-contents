# Zenn CLI

* [📘 How to use](https://zenn.dev/zenn/articles/zenn-cli-guide)

## 導入手順
- フォルダ構成
    ```
    articles/
    ├─ .devcontainer/
    │    └─ devcontainer.json  # コンテナ設定ファイル
    ├─ zenn-contents/          # Zenn記事用ディレクトリ (Gitリポジトリ)
    └─ qiita-contents/         # Qiita記事用ディレクトリ (Gitリポジトリ)
    ```

-  `devcontainer.json`
    ファイルを作成して `articles/` をVSCodeで開き，必要なパッケージ（`Dev Containers`）をインストールすれば完了．
    ```
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
   1. 新規作成する場合
   ```
   cd qiita-contents
   npm init --yes
   npm install @qiita/qiita-cli --save-dev
   npx qiita init
   ```

   2. GitHubからインストールした場合
   ```
   cd qiita-contents
   npm install
   ```
