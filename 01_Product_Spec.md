# 01_Product_Spec (v0.1)

## 1. Product Brief
- 目的（1文）:
- ターゲット/ペルソナ:
- 世界観/トーン（例：禅/テック/ポップ）:
- KPI（北極星）: 例) D1留存, セッション/日
- スコープ
  - In: 
  - Out:
- MVP（3点まで）:

> 質問: このアプリが解消する**最も強い痛み**は何？ユーザーの「前/後」を一言で？

## 2. User Flows & Navigation
- 主要フロー（箇条書き→後で図）
- 例外分岐（通信失敗/未認証/空データ）
- DeepLink/マルチシーン要否

> 質問: エラー時は**再試行**/ドラフト保存/案内どれを優先？

## 3. Domain Model（SwiftData想定）
### 3.1 Entities（一意制約/索引/関係）
- `EntityName`: 属性名:型(制約), …
- 関係: 1:多 / 多:多（中間テーブル方針）
- インデックス: …
- サンプルFixtures(JSON 3件)

> 質問: タグ/カテゴリは**複数選択**？並び順の**安定キー**は必要？

## 4. State Management & Architecture（要点）
- 採用: Actor + MVVM（ViewはStateless、VMは@MainActor）
- 非同期: AsyncStream(イベント)/Task cancellation規約
- 確定ルール: `@StateObject`の初期化はView initで注入しない

> 質問: どの状態は**アプリ全域で共有**？（例：Auth/UserSettings）

## 5. UI Components（Design System + Reusable Views）
- 色/タイポ/Spacingトークン（例: `Spacing.s, m, l`）
- コンポーネント仕様（Props/イベント/例）
  - Button, TagChip, EmptyState, Toast, Loading, ErrorView
- アクセシビリティ（DynamicType/VoiceOver/コントラスト）

> 質問: iPad対応は？SplitViewやPopoverは使う？

## 6. Layouts（主要画面）
- Home / Detail / Editor / Settings（各1段落＋スケッチ）
- 回転/サイズクラス対応の方針

> 質問: 一覧の最大件数や無限スクロールの閾値は？

## 7. Definition of Done（DoD）
- 起動<1.2s / スクロール60fps / 空状態/エラーのUI完備/Unit+Snapshot必須

## 8. Changelog
- v0.1: 初版
