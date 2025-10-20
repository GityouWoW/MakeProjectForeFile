# 03_Quality_Ops (v0.1)
- 以下の未決定項目を決めていきましょう。

## 1. Testing Strategy
- 単体（UseCase/Formatter/Validator）
- Snapshot（主要画面）
- UIテスト（Happy path + 代表エラー）
- 最低ゲート: Unit ≥80%/Snapshot主要View完了

> 質問: どの画面を**Snapshot優先**に？（上位3つ）

## 2. CI/CD & Release
- CI（lint, build, unit, snapshot）→ TestFlight → 本番
- バージョニング / Feature Flag運用

## 3. Operations（ログ/障害対応）
- アラート条件（クラッシュ率/起動失敗率）
- ロールバック手順/緊急フラグ制御

## 4. Error Playbook（頻出・即対応集）
- `Escaping autoclosure captures mutating 'self'`  
  - 原因: struct内のescapingでselfキャプチャ  
  - 対処: 非mutating化/Actor委譲/`[weak self]`
- `Variable 'self.viewModel' used before being initialized`  
  - 対処: `_vm = StateObject(wrappedValue:)` をinitで明示
- `Non-class type 'View' cannot conform to class protocol`  
  - 対処: デリゲート→クロージャ/ObservableObjectへ
- `Publishing changes from background threads is not allowed`  
  - 対処: `@MainActor`/`MainActor.run`/`receive(on:)`
- `Modifying state during view update`
  - 対処: `task{}`開始/遅延/Transaction境界整理
- `Fatal error: No ObservableObject of type ... found`
  - 対処: `environmentObject`注入漏れ/Preview差分

> 質問: どのエラーは**発見したら即CI落とす**？（3つ）

## 5. Compliance & Privacy
- 許諾文言（権限/課金/トラッキング）  
- データ保持/削除要請の窓口/手順

> 質問: **データ削除依頼**をアプリ内から受け付ける？

## 6. Checklist（出荷前）
- 起動時間/空状態/エラーUI/アクセシビリティ/ローカライズ/価格表記

## 7. Changelog
- v0.1: 初版
