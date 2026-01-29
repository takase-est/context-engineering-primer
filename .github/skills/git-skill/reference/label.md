# ラベル管理

GitHubのラベルを管理する手順です。

## 前提条件

- GitHub CLI (`gh`) がインストールされていること
- リポジトリへの書き込み権限があること

## 基本的な流れ

1. 既存ラベルの確認
2. ラベルの作成・更新・削除
3. ラベルの使用

## 手順

### 1. 既存ラベルを確認

**ラベル一覧を表示:**
```bash
gh label list
```

**詳細表示（色コード含む）:**
```bash
gh label list --limit 100
```

### 2. ラベルの作成

**基本的な作成:**
```bash
gh label create "ラベル名"
```

**説明と色を指定:**
```bash
gh label create "bug" --description "バグ報告" --color "d73a4a"
```

**対話的に作成:**
```bash
gh label create
```

### 3. ラベルの詳細を確認

```bash
gh label view "ラベル名"
```

### 4. ラベルの更新

**名前を変更:**
```bash
gh label edit "古い名前" --name "新しい名前"
```

**説明を更新:**
```bash
gh label edit "bug" --description "バグ・不具合の報告"
```

**色を更新:**
```bash
gh label edit "bug" --color "ff0000"
```

### 5. ラベルの削除

```bash
gh label delete "ラベル名"
```

**確認なしで削除:**
```bash
gh label delete "ラベル名" --yes
```

## Conventional Commits形式のラベル

このリポジトリでは、Conventional Commits形式に準拠したラベルを使用します。

**詳細なラベル一覧は[ラベル定義](labels-definition.md)を参照してください。**

### 利用可能なラベル（クイックリファレンス）

- **変更の種類**: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
- **作業項目**: `task`

各ラベルの詳細な説明、色コード、使用例については[ラベル定義](labels-definition.md)を参照してください。

## ラベルの一括作成

新しいリポジトリで標準ラベルをセットアップする場合は、[ラベル定義](labels-definition.md)に記載されている一括作成スクリプトを使用してください。

## IssueやPRへのラベル付与

### Issueにラベルを追加

```bash
gh issue edit 123 --add-label "fix"
```

### Issueからラベルを削除

```bash
gh issue edit 123 --remove-label "fix"
```

### PRにラベルを追加

```bash
gh pr edit 456 --add-label "feat"
```

## ラベルの使用パターン

ラベルの使用パターンについては、[ラベル定義](labels-definition.md)の「ラベルの使用パターン」セクションを参照してください。

### ラベルによる絞り込み

**特定のラベルでIssueを検索:**
```bash
gh issue list --label "fix"
```

**複数ラベルでAND検索:**
```bash
gh issue list --label "task,feat"
```

## ラベルのベストプラクティス

### 1. Conventional Commitsに準拠

- ラベル名はConventional Commits形式を使用
- `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`, `task`を主要カテゴリとして使用

### 2. 重複ラベルの統合

詳細は[ラベル定義](labels-definition.md)の「既存ラベルの統合（マイグレーション）」セクションを参照してください。

### 3. 一貫性を保つ

- **ラベル名** - 英語（短いキーワード）で統一
- **説明** - プロジェクトの主要言語（英語/日本語）で統一
- **色コード** - Conventional Commits形式に準拠した色を使用

### 4. 早めに付与する

Issue や PR を作成したら、すぐに適切なラベルを付与しましょう。

### 5. Task IssueのDoDを確認

Task IssueのPRを作成する場合は、Issueの完了条件・受け入れ基準（DoD）をすべて満たしていることを確認してください。

## トラブルシューティング

### ラベルが削除できない

**原因:** 使用中のラベルを削除しようとしている

**確認方法:**
```bash
gh issue list --label "削除したいラベル名"
gh pr list --label "削除したいラベル名"
```

使用中の場合は、先にIssue/PRから削除してください。

### ラベルの色コードがわからない

**参考:**
- GitHub公式のデフォルト色を参照
- カラーピッカーツールを使用（例: https://htmlcolorcodes.com/）
- 16進数カラーコード（例: `#d73a4a`の`#`なし → `d73a4a`）

### ラベルが重複している

**確認:**
```bash
gh label list | grep "ラベル名"
```

大文字小文字やスペースの違いに注意してください。

## 高度な使い方

### ラベルのエクスポート

```bash
gh label list --json name,description,color > labels.json
```

### 他のリポジトリにラベルをインポート

1. エクスポートしたJSONファイルを編集
2. スクリプトで一括作成

```bash
# JSONから読み込んで作成するスクリプト例
jq -r '.[] | "gh label create \"\(.name)\" --description \"\(.description)\" --color \"\(.color)\""' labels.json | bash
```
