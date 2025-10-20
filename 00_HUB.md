# 00_HUB (v0.1)

## 目的
SwiftUIベースの中規模iOSアプリを、GPT5Thinkと共同で設計〜運用まで迷子なく進めるためのハブ。

## 進め方（推奨フロー）
1. 01_Product_Spec.md を完成（MVP/モデル/フロー/主要UI）
2. 02_Integration.md を確定（API/ロジック/課金/認証）
3. 03_Quality_Ops.md を整備（テスト/配布/運用/法務・エラー）

## 依頼テンプレ（GPT5Think向け）
### 🧭 Context
- 進行ファイル: 01_Product_Spec.md / セクション: Domain→Entities

### 🎯 Goal
- SwiftDataモデルの定義と一意制約の決定

### 📚 Reference
- 01_Product_Spec.md「MVP」「UserFlows」

### 🪄 Output
- 完成コード（貼付可）
- 差分Markdown
- 落とし穴リスト（3件）

### ❓Question（GPTからの逆質問を促す）
- 代替案があるなら提示してから選択質問を返して

## 目次
- 01_Product_Spec.md … 企画/UX/Domain/UI
- 02_Integration.md … API/Logic/StoreKit2/Auth
- 03_Quality_Ops.md … Test/CI/Release/Logs/Error/Privacy

## 次へ進むためのクイック質問
1) このアプリのMVPで**絶対に外せない3機能**は？  
2) 主要ユーザーの**達成したい行動**は1セッションで何分？  
3) オフライン動作の必要度（不要 / 最低限 / 重要）？

