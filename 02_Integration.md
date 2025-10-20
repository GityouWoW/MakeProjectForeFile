# 02_Integration (v0.1)
- 以下の未決定項目をすべて決めたいきましょう。

## 1. API Spec（外部/内部）
- ベースURL / 認証方式 / Rate Limit
- エンドポイント表（Path, Method, Req/Res, Errors）
- リトライ＆バックオフ / 失敗→フォールバック（キャッシュ/ドラフト）

> 質問: **オフラインキャッシュ**は必要？有効期限は？

## 2. Business Logic（UseCases）
- 代表ユースケース: 取得/保存/同期/検索
- 失敗境界: ネットワーク/検証/権限

> 質問: 競合（ローカル vs サーバ）の**勝者ルール**は？

## 3. Auth & Security
- Keychain/Secure Enclave 利用箇所
- トークン更新フロー / 期限切れUI
- 最小権限原則（スコープ）

> 質問: ゲスト利用は許可？機能制限は？

## 4. StoreKit2（課金）
- 商品表(IDs, 価格, ベネフィット) / 導線
- 購読状態の判定・機能ゲート
- 購読切れ時UI/復元/返金ポリシー要約

> 質問: 無料→有料の移行で**既存データ**は保持？

## 5. Telemetry
- OSLog分類（debug/info/error）, MetricKit
- 重要イベント（課金/同期/致命エラー）

## 6. Changelog
- v0.1: 初版
