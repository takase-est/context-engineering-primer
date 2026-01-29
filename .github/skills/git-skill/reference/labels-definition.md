# ラベル定義

このリポジトリで使用するConventional Commits形式のラベル一覧です。

**Issue作成・PR作成時は、必ずこのリストから選択してください。**

## Conventional Commits タイプについて

各ラベルのタイプ（`feat`, `fix`, `docs`など）の詳細な説明と使用例については、[Conventional Commits タイプ定義](conventional-commits-types.md)を参照してください。

## ラベル一覧（色コード付き）

### 変更の種類（Type）

| ラベル名 | 色コード | 説明 |
|---------|---------|------|
| feat | 0e8a16 | 新機能 |
| fix | d73a4a | バグ修正 |
| docs | 0075ca | ドキュメントのみの変更 |
| style | c5def5 | コードの動作に影響しない変更 |
| refactor | a2eeef | リファクタリング |
| perf | fbca04 | パフォーマンス改善 |
| test | 0e8a16 | テストの追加・修正 |
| build | d876e3 | ビルドシステムや外部依存関係の変更 |
| ci | 1d76db | CI/CD設定やスクリプトの変更 |
| chore | ffffff | その他の変更 |
| revert | ffffff | 以前のコミットの取り消し |

### 作業項目（Task）

| ラベル名 | 色コード | 説明 |
|---------|---------|------|
| task | 1d76db | 開発タスクや改善タスク |

**Task Issueでの使用:**
- Task IssueのPRでは、`task`ラベルと実際の変更内容に応じたラベルを併用
- 例: `task` + `feat`、`task` + `fix`、`task` + `refactor`

## ラベルの使用パターン

### Issueでの使用

- バグ報告 → `fix`
- 機能要望 → `feat`
- ドキュメント改善 → `docs`
- Task Issue → `task`

### Pull Requestでの使用

- 新機能の実装 → `feat`
- バグ修正 → `fix`
- リファクタリング → `refactor`

### 複数ラベルの併用

1つのIssue/PRに複数のラベルを付けることで、より詳細な分類が可能です。

**推奨される併用パターン:**

1. **Task Issue関連のPR**
   - `task` + `feat` - Task Issueで新機能を実装
   - `task` + `fix` - Task Issueでバグ修正
   - `task` + `refactor` - Task Issueでリファクタリング

2. **複数の変更を含むPR**
   - `feat` + `docs` - 新機能の実装とドキュメントの追加
   - `fix` + `test` - バグ修正とテストの追加
   - `refactor` + `perf` - リファクタリングとパフォーマンス改善

**注意:** 基本的には1つのPRで1つの目的を達成することを推奨します。複数のラベルが必要な場合は、PRを分割できないか検討してください。

## ラベル一括作成スクリプト

新しいリポジトリでラベルをセットアップする場合、以下のスクリプトを使用してください。

```bash
#!/bin/bash

# 変更の種類（Type）
gh label create "feat" --description "新機能" --color "0e8a16"
gh label create "fix" --description "バグ修正" --color "d73a4a"
gh label create "docs" --description "ドキュメントのみの変更" --color "0075ca"
gh label create "style" --description "コードの動作に影響しない変更" --color "c5def5"
gh label create "refactor" --description "リファクタリング" --color "a2eeef"
gh label create "perf" --description "パフォーマンス改善" --color "fbca04"
gh label create "test" --description "テストの追加・修正" --color "0e8a16"
gh label create "build" --description "ビルドシステムや外部依存関係の変更" --color "d876e3"
gh label create "ci" --description "CI/CD設定やスクリプトの変更" --color "1d76db"
gh label create "chore" --description "その他の変更" --color "ffffff"
gh label create "revert" --description "以前のコミットの取り消し" --color "ffffff"

# 作業項目（Task）
gh label create "task" --description "開発タスクや改善タスク" --color "1d76db"
```

実行:
```bash
chmod +x create-labels.sh
./create-labels.sh
```

## 既存ラベルの統合（マイグレーション）

古いラベルは統合してください:
- `documentation` → `docs`
- `bug` → `fix`
- `enhancement` → `feat`
