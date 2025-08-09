# Template ID: 0006 - Cursor AI統合Marp作成ガイド

CursorのAIアシスタント機能を最大限活用して、効率的なMarpスライド生成を実現するワークフローです。

## 🤖 AI活用の特徴

### CursorAI統合機能
- **@ファイル参照**: `@Marpスライド生成ルール.md`でルール適用
- **AI Chat**: リアルタイムでスライド内容生成・修正
- **Tab補完**: AI支援による高速コーディング
- **Composer機能**: 複数ファイル同時編集

### 🎯 AI駆動ワークフロー

```mermaid
graph LR
    A[元資料] --> B[AI要約]
    B --> C[構造化]
    C --> D[Marp生成]
    D --> E[AI校正]
    E --> F[完成]
```

## 📁 Cursor特化ファイル構造

```
workspace/
├── .cursor/
│   ├── settings.json                  # AI設定最適化
│   └── rules.md                       # カスタムルール
├── .cursorrules                       # AI動作ルール
├── templates/
│   ├── @Marpスライド生成ルール.md          # AI参照用ルール
│   └── @Marpテンプレート_基本.md           # AI参照用テンプレート
└── slides/
    ├── draft/                         # AI生成ドラフト置き場
    └── final/                         # 完成版置き場
```

## 🚀 CursorAI専用セットアップ

### 1. Cursor設定最適化
```json
// .cursor/settings.json
{
  "cursor.ai.model": "claude-3.5-sonnet",
  "cursor.ai.enableTabCompletion": true,
  "cursor.ai.enableChat": true,
  "markdown.marp.enabled": true,
  "markdown.marp.themes": [
    "default",
    "gradient"
  ]
}
```

### 2. AI支援機能設定
- **Composer**: 複数ファイル編集モード有効化
- **Chat履歴**: スライド生成プロセスの記録
- **@ルール参照**: 自動的なルール適用

### 2. テーマ設定（オプション）
VS CodeのSettings > Markdown > Marp: Themesに以下を追加：
```
https://cunhapaulo.github.io/style/freud.css
```

### 3. 人気のテーマ
- gradient
- beamer
- border
- dracula
- speee
- plato
- heidegger

## 🎯 CursorAI活用ワークフロー

### Step 1: AI支援による資料分析
1. **元資料をCursorに読み込み**
   ```
   @[資料ファイル名].md の内容を分析してスライド構成を提案してください
   ```

2. **AI による構造化提案**
   - 自動的な章立て提案
   - 重要度による優先順位付け
   - スライド枚数の最適化提案

### Step 2: AI統合ルール適用
```
@Marpスライド生成ルール.md と @Marpテンプレート_基本.md を参照して、
以下の資料からプロフェッショナルなスライドを生成してください：

[資料内容をペースト]

要件:
- 聴衆レベル: [初心者/中級者/上級者]
- 発表時間: [分数]
- 重点項目: [強調したいポイント]
```

### Step 3: AIリアルタイム校正
- **Tab補完**: コード部分の自動補完
- **Chat校正**: 「このスライドの表現をより分かりやすく」
- **Composer**: 複数スライドの同時調整

## 📋 生成されるスライドの特徴

- **形式**: 16:9ワイド形式
- **スタイル**: 上下黒縁 + アクセントライン
- **フォント**: Noto Sans JP（日本語最適化）
- **構成**: タイトル → アジェンダ → 本文 → まとめ
- **文字数**: 見出し13文字以内、適切な情報量

## 🖼️ 画像の使用

1. 画像ファイルを`CursorCourse/Chapter3_Presentation/images/`ディレクトリに配置
2. スライドでは相対パス`./images/filename.png`で参照
3. ロゴ画像は推奨

## ⚠️ 注意事項

### 日本語対応
- フォント: 'Noto Sans JP'使用
- 文字化け防止のためのエンコーディング対応

### スライド品質
- 1スライドあたり最大5個の要点
- 表は4列以内
- 箇条書きは2階層まで

### ファイル命名
- 自動生成されるファイル名: `YYYYMMDD_タイトル.md`
- 手動での調整も可能

## 🛠️ カスタマイズ

### テンプレートの編集
- `Marpテンプレート_基本.md`: 基本構造のカスタマイズ
- `CursorCourse/Chapter3_Presentation/slides/marp_template.md`: 実習用テンプレート

### ルールの調整
- `Marpスライド生成ルール.md`: 生成ルールの変更

## 🤖 AI活用実例

### Case 1: 技術ドキュメントからスライド生成
```
AI指示例:
「@技術仕様書.md を元に、エンジニア向け15分プレゼン用のスライドを作成。
実装のポイントとコード例を中心に、視覚的に分かりやすく。」

AI出力: 
- 自動的な技術要素の抽出
- コードハイライト付きスライド
- アーキテクチャ図の提案
```

### Case 2: 会議資料の効率的変換
```
AI指示例:
「@議事録.md から重要な決定事項を抽出し、
ステークホルダー向け報告スライドを5枚で作成」

AI出力:
- 決定事項の自動優先順位付け
- 視覚的なタイムライン作成
- アクションアイテムの表組み化
```

### Case 3: リアルタイム内容調整
```
Chat活用:
- 「このスライドをもっと視覚的に」
- 「専門用語を初心者向けに調整」  
- 「グラフを追加して数値を強調」
→ リアルタイムで内容が改善される
```

## 💡 CursorAI最適化Tips

### プロンプト最適化
- **具体的な指示**: 「15分、エンジニア向け、実装重視」
- **段階的改善**: 「まず骨格を作って、次に詳細を」
- **@参照活用**: 既存テンプレート・ルールの自動適用

### 効率化テクニック
- **Composer使用**: 複数スライドを同時編集
- **Chat履歴**: 過去の生成パターンを再利用
- **Tab補完**: コード・数式の高速入力

## 🔗 CursorAI関連リンク

- [Cursor公式ドキュメント](https://docs.cursor.com/)
- [AI Prompt Best Practices](https://docs.cursor.com/prompting)
- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
- [Claude 3.5 Sonnet活用ガイド](https://docs.anthropic.com/claude/docs)

---

## 📝 更新履歴

| バージョン | 日付 | 変更内容 | 変更者 |
|-----------|------|----------|---------|
| 2.0.0 | 2025-01-28 | CursorAI特化版に全面改訂・AI活用ワークフロー追加 | AI Enhancement |
| 1.0.0 | 2025-07-15 | 初回作成 | Template Team |

---

最終更新: 2025-01-28 17:30:00 JST