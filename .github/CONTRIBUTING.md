# 開発ガイドライン

このリポジトリへの貢献にご協力いただき、ありがとうございます。  
以下のガイドラインに従って開発を進めてください。

## ブランチ戦略

### 基本方針
このシステムは`main`ブランチから直接作業ブランチを切って開発を行います。

```
main（本番） ← feature/xxx
```

### 開発フロー
1. `main`ブランチから作業ブランチを作成
2. 機能開発・修正を実施
3. プルリクエストを作成
4. レビュー後、`main`ブランチにマージ
5. 作業ブランチを削除

### 注意事項
- `main`ブランチに直接pushは禁止
- 必ずプルリクエストを通してマージ
- 小さい単位で開発し、リスクを最小化

## ブランチ名

### 基本形式
```
種類/簡潔な説明
```
または
```
種類/issue番号-簡潔な説明
```

### 種類の分類
- `feature/` - 新機能の追加
- `fix/` - バグ修正
- `hotfix/` - 緊急修正
- `refactor/` - リファクタリング
- `docs/` - ドキュメント更新
- `test/` - テストの追加・修正

### 具体例
```
feature/user-authentication
fix/login-button-styling
hotfix/payment-api-error
feature/123-add-search-functionality
refactor/api-client-class
docs/update-readme
test/add-unit-tests
```

## コミットメッセージ

### 基本形式
```
動詞: 何をしたかの説明 (#issue番号)
```

### 動詞の使い分け
- `add:` - 新機能、新ファイルの追加
- `fix:` - バグ修正
- `update:` - 既存機能の更新、改善
- `remove:` - ファイルや機能の削除
- `refactor:` - コードの整理、リファクタリング
- `docs:` - ドキュメントの更新
- `test:` - テストの追加・修正

### 具体例
```
add: ユーザー認証機能を追加 (#123)
fix: ログインボタンのスタイル崩れを修正 (#124)
update: READMEにインストール手順を追加
remove: 不要なライブラリを削除
refactor: API呼び出し部分をクラス化
docs: APIドキュメントを更新
test: ユーザー認証のテストケースを追加
```

## プルリクエスト

### タイトル
ブランチ名と同様の形式で記載してください。

### 本文テンプレート
```markdown
## 概要
何をしたかの簡潔な説明

## 変更内容
- 変更点1
- 変更点2
- 変更点3

## 関連Issue
Closes #123
Fixes #124

## 動作確認
- [ ] 確認項目1
- [ ] 確認項目2
- [ ] 確認項目3

## 備考
レビューで特に見てほしい点があれば記載
```

## Issue番号の参照

### 自動リンク
コミットメッセージやPRにissue番号を含めると、自動的にリンクされます。

```
fix: ログインエラーを修正 (#123)
```

### 自動クローズ
以下のキーワードを使うと、PRがマージされた時にissueも自動的にクローズされます。

- `fixes #123`
- `closes #123`
- `resolves #123`

### 実践例
Issue #123「ログインできない」がある場合：
- ブランチ: `fix/123-login-error`
- コミット: `fix: ログイン時のバリデーションエラーを修正 (#123)`
- PR: 「ログインエラーの修正 (fixes #123)」

## レビュープロセス

1. プルリクエストを作成
2. 最低1人のレビュアーを指定
3. 動作確認を実施（本番環境リリース前の最終確認）
4. レビュー承認後にマージ
5. マージ後は作業ブランチを削除

## 注意事項

- `main`ブランチに直接pushは禁止
- 大きな変更の場合は事前にissueで相談
- コミットは細かく分けて、わかりやすい単位で行う
- 問題が発生した場合は`hotfix/`ブランチで緊急対応
- 小さい単位でのリリースを心がけ、リスクを最小化
