# Conventional Commits タイプ定義

このファイルは、Conventional Commits形式で使用するタイプの一覧です。
ブランチ命名、コミットメッセージ、ラベル、PRタイトルなど、すべての場面で共通して使用します。

## タイプ一覧

| タイプ | 説明 | 使用例 |
|--------|------|--------|
| **feat** | 新機能 | 新しいAPIエンドポイント、新しいUIコンポーネント |
| **fix** | バグ修正 | クラッシュの修正、誤った動作の是正 |
| **docs** | ドキュメントのみの変更 | READMEの更新、コメントの追加 |
| **style** | コードの動作に影響しない変更 | フォーマット、空白、セミコロン |
| **refactor** | リファクタリング | 関数の分割、変数名の改善 |
| **perf** | パフォーマンス改善 | アルゴリズムの最適化、キャッシュの導入 |
| **test** | テストの追加・修正 | ユニットテストの追加、E2Eテストの改善 |
| **build** | ビルドシステムや外部依存関係の変更 | package.jsonの更新、webpack設定の変更 |
| **ci** | CI/CD設定やスクリプトの変更 | GitHub Actionsの追加・修正 |
| **chore** | その他の変更 | .gitignoreの更新、設定ファイルの微調整 |
| **revert** | 以前のコミットの取り消し | 問題のあるマージのrevert |

## 作業項目タイプ

| タイプ | 説明 | 使用場面 |
|--------|------|----------|
| **task** | 開発タスクや改善タスク | Task Issue、複数の変更を含む作業 |

**Task タイプの特徴:**
- Task IssueのPRでは、`task`と実際の変更内容に応じたタイプを併用します
- 例: `task` + `feat`、`task` + `fix`、`task` + `refactor`

## 使用場面

このタイプ定義は以下の場面で使用します：

1. **ブランチ名**: `<type>/<description>` (例: `feat/add-csv-import`)
2. **コミットメッセージ**: `<type>: <description>` (例: `feat: CSVインポート機能を追加`)
3. **GitHubラベル**: `feat`, `fix`, `docs`など
4. **PRタイトル**: コミットメッセージと同様の形式

## クイックリファレンス

**変更の種類（よく使うもの）:**
- `feat` - 新機能
- `fix` - バグ修正
- `docs` - ドキュメント
- `refactor` - リファクタリング
- `test` - テスト

**その他:**
- `style` - コードスタイル
- `perf` - パフォーマンス
- `build` - ビルド設定
- `ci` - CI/CD
- `chore` - その他
- `revert` - 取り消し

**作業項目:**
- `task` - Task Issue

## タイプの選び方

### 迷った時の判断基準

1. **新しい機能を追加** → `feat`
2. **既存の機能が正しく動作しない** → `fix`
3. **コードの動作は変わらないが構造を改善** → `refactor`
4. **ドキュメントだけの変更** → `docs`
5. **テストだけの変更** → `test`
6. **複数の種類を含むTask** → `task` + メインのタイプ

### 複数のタイプにまたがる場合

**基本原則**: 1つのPR/Issue/ブランチで1つの目的を達成する

**やむを得ず複数含む場合:**
- **PRラベル**: メインのタイプ + サブのタイプ（例: `feat` + `docs`）
- **ブランチ名**: メインのタイプを使用（例: `feat/add-user-auth`）
- **コミットメッセージ**: コミットごとに適切なタイプを使用

**Task Issueの場合:**
- ラベル: `task` + メインのタイプ
- ブランチ名: メインのタイプ（例: `feat/add-user-auth`）

## 参考資料

- [Conventional Commits 仕様](https://www.conventionalcommits.org/ja/)
- [Angular コミット規約](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#-commit-message-format)
