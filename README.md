# devcontainer

[DevContainer][devcontainer] 向けの Docker イメージを GHCR (GitHub Container Registry) に publish するリポジトリ。

# Docker Images

## devcontainer-node

NodeJS の利用を目的としたベースイメージ。

### DevContainer 設定例

```json
{
  "name": "xxx",
  "image": "ghcr.io/yu-ogi/devcontainer-node:latest",
  "remoteUser": "node",
  "workspaceMount": "source=${localWorkspaceFolder},target=/workspace,type=bind,consistency=delegated",
  "workspaceFolder": "/workspace"
}
```

# publish

1. [Actions](./actions) タブから `Publish Docker Image` ワークフローを選択します。
2. `Run workflow` ボタンを押して、以下の input を設定のうえ実行してください。
   - `dockerfile_variant`
     - ビルド対象の Dockerfile バリエーション
   - `tag`
     - Docker イメージのタグ
       - 未指定の場合は `YYMMDD`の形式で実行時の日付から自動生成
       - タグ値は `[A-Za-z0-9_.-]+` のみを許可します
   - `latest`
     - latest タグを付与するかどうか

[devcontainer]: https://containers.dev/
