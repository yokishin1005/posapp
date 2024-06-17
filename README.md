
# プロジェクト名

このプロジェクトは、Next.jsを使用したフロントエンドとFastAPIを使用したバックエンドを持つWebアプリケーションです。

## プロジェクト構成

- [フロントエンド](#フロントエンド)
- [バックエンド](#バックエンド)
- [Docker](#docker)

## フロントエンド

フロントエンドはNext.jsを使用して構築されています。

### ディレクトリ構成

- `/public`: 画像、アイコン、フォントなどの静的ファイルを配置します。
- `/components`: 再利用可能なReactコンポーネントを配置します。
- `/pages`: ページコンポーネントを配置します。Next.jsのルーティングはこのディレクトリによって自動的に管理されます。
- `/styles`: CSSやSassファイルを配置します。
- `/utils`: ユーティリティ関数やヘルパー関数を配置します。
- `next.config.js`: Next.jsの設定ファイルです。
- `package.json`: プロジェクトの依存関係とスクリプトを定義します。

### ファイルの機能

- `next.config.js`: Next.jsの設定を管理するファイル。
- `package.json`: プロジェクトの依存関係やスクリプトを管理するファイル。

### セットアップと実行

1. 依存関係をインストールします。
   ```bash
   npm install
   ```

2. 開発サーバーを起動します。
   ```bash
   npm run dev
   ```

## バックエンド

バックエンドはFastAPIを使用して構築されています。

### ディレクトリ構成

- `/app/api/v1`: APIエンドポイントを定義するディレクトリです。
  - `products.py`: 製品に関連するAPIエンドポイント（登録、更新、削除、取得）を定義します。
  - `transactions.py`: 取引に関連するAPIエンドポイント（作成、更新、取得）を定義します。
  - `items.py`: アイテムに関連するAPIエンドポイント（追加、削除、取得）を定義します。
- `/app/core`: アプリケーションの基本設定を管理するディレクトリです。
  - `config.py`: アプリケーションの設定情報（データベース接続設定など）を定義します。
- `/app/db`: データベースに関連するファイルを管理するディレクトリです。
  - `models.py`: データベースのテーブル構造（製品、取引、アイテム）を定義します。
  - `session.py`: データベースセッションの管理を行います。
- `/app/schemas`: リクエストとレスポンスのデータ構造を定義するディレクトリです。
  - `product.py`: 製品に関連するデータのスキーマを定義します。
  - `transaction.py`: 取引に関連するデータのスキーマを定義します。
  - `item.py`: アイテムに関連するデータのスキーマを定義します。
- `/app/services`: ビジネスロジックを管理するディレクトリです。
  - `product_service.py`: 製品に関連するビジネスロジック（価格計算、在庫管理など）を実装します。
  - `transaction_service.py`: 取引に関連するビジネスロジック（合計金額の計算、取引履歴の管理など）を実装します。
- `/tests`: テストを管理するディレクトリです。
  - `/unit`: 単体テストを管理します。個々の機能やモジュールのテストを行います。
  - `/integration`: 統合テストを管理します。複数のモジュールの連携をテストします。
- `main.py`: FastAPIアプリケーションのエントリーポイントです。アプリケーションの起動やAPIエンドポイントの登録を行います。
- `requirements.txt`: プロジェクトで使用するPythonの依存関係を定義します。

### ファイルの機能

- `products.py`: 製品に関連するAPIエンドポイントを定義します。製品の登録、更新、削除、取得などの操作を行います。
- `transactions.py`: 取引に関連するAPIエンドポイントを定義します。取引の作成、更新、取得などの操作を行います。
- `items.py`: アイテムに関連するAPIエンドポイントを定義します。アイテムの追加、削除、取得などの操作を行います。
- `config.py`: アプリケーションの設定情報を定義します。データベース接続設定などの基本的な設定情報を管理します。
- `models.py`: データベースのテーブル構造を定義します。製品、取引、アイテムのテーブルを設定します。
- `session.py`: データベースセッションの管理を行います。データベースとの接続を作成し、クエリを実行するための設定を行います。
- `product.py`: 製品に関連するデータのスキーマを定義します。製品の名前や価格などのフィールドを設定します。
- `transaction.py`: 取引に関連するデータのスキーマを定義します。取引の日時や合計金額などのフィールドを設定します。
- `item.py`: アイテムに関連するデータのスキーマを定義します。アイテムの製品IDや取引ID、数量などのフィールドを設定します。
- `product_service.py`: 製品に関連するビジネスロジックを実装します。価格計算や在庫管理などの操作を行います。
- `transaction_service.py`: 取引に関連するビジネスロジックを実装します。取引の合計金額の計算や取引履歴の管理などの操作を行います。
- `main.py`: FastAPIアプリケーションのエントリーポイント。アプリケーションの起動やAPIエンドポイントの登録を行います。
- `requirements.txt`: プロジェクトで使用するPythonの依存関係を定義します。

### セットアップと実行

1. 仮想環境を作成し、アクティベートします。
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windowsの場合は `venv\Scripts\activate`
   ```

2. 依存関係をインストールします。
   ```bash
   pip install -r requirements.txt
   ```

3. 開発サーバーを起動します。
   ```bash
   uvicorn main:app --reload
   ```
