---
name: git-skill
description: |
  Conventional Commits形式に準拠したGit/GitHub運用を支援するスキル。
  以下のGit/GitHub操作が必要な時に自動的に使用：
  - `git commit` - Conventional Commits形式でのコミット（feat:, fix:, docs:など）
  - `git push` - リモートへのプッシュ（-uフラグ、force pushの判断）
  - `gh pr create` - プルリクエスト作成（ブランチ命名規則、ラベル付け、DoDの確認）
  - `gh issue create` - Issue作成（適切なラベル付け、Task IssueのDoD設定）
  - `gh label` - ラベル管理（create, edit, delete, list）
  - `git checkout -b` - ブランチ作成（命名規則：feat/, fix/, docs/など）
---

# Git/GitHub運用スキル

このスキルは、Conventional Commits形式に準拠した日常的なGit/GitHub操作を支援します。

## いつ使うか

以下のGit/GitHub操作が必要な時に自動的に使用されます：

- **`git commit`**: コード変更後のコミット（Conventional Commits形式）
- **`git push`**: リモートへのプッシュ（upstream設定、force pushの判断）
- **`gh pr create`**: プルリクエスト作成（ブランチ命名規則、ラベル付け、DoDの確認）
- **`gh issue create`**: Issue作成（適切なラベル付け、Task IssueのDoD設定）
- **`gh label create/edit/delete/list`**: GitHubラベル管理
- **`git checkout -b`**: 新規ブランチ作成（命名規則：feat/, fix/, docs/など）

## このスキルができること

- **コミット・プッシュ** - 変更のコミットとリモートへのプッシュ
- **PR作成** - プルリクエストの作成（ブランチ命名規則、ラベル付け、DoDの確認）
- **Issue作成** - Issueの作成（適切なラベル付け、Task IssueのDoD設定）
- **ラベル管理** - Conventional Commits形式のラベルの作成、更新、削除、一覧表示

## 詳細手順

各操作の詳細は以下のリファレンスを参照してください：

### 基本リファレンス
- [Conventional Commits タイプ定義](reference/conventional-commits-types.md) - タイプの詳細な説明と使い分け（すべての操作の基礎）
- [ラベル定義](reference/labels-definition.md) - 利用可能なラベル一覧（色コード付き）

### 操作リファレンス
- [ブランチ操作](reference/branch.md) - ブランチの作成、切り替え、削除、命名規則
- [コミット](reference/commit.md) - 変更のコミット方法
- [プッシュ](reference/push.md) - リモートへのプッシュ方法
- [PR作成](reference/pr.md) - プルリクエストの作成方法
- [Issue作成](reference/issue.md) - Issueの作成方法
- [ラベル管理](reference/label.md) - ラベルの管理方法

## 使用方法

このスキルを呼び出すには、以下のように指示してください：

```
git-skillを使用してコミットとプッシュを行ってください
```

```
git-skillを使用してPRを作成してください
```

```
git-skillを使用してラベルを確認してください
```

## 必要なツール

- Git
- GitHub CLI (`gh`) - PR、Issue、ラベル操作に推奨
