---
marp: true
size: 16:9
paginate: true
backgroundColor: "var(--color-bg)"
theme: default

style: |
  @import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;700;900&display=swap");
  :root {
    --color-bg:      #fafbfc;
    --color-text:    #2c3e50;
    --color-accent:  #3498db;
    --color-secondary: #e74c3c;
    --color-border:  #34495e;
    --color-light:   #ecf0f1;
    --color-dark:    #2c3e50;
    --border-h: 50px;
    --pad-v: 7%;
    --pad-h: 9%;
    --fs-title: 56pt;
    --fs-h2:    40pt;
    --fs-body:  26pt;
    --fs-note:  20pt;
  }

  section {
    font-family: "Noto Sans JP", sans-serif;
    color: var(--color-text);
    background: linear-gradient(135deg, #fafbfc 0%, #f8f9fa 100%);
    padding: var(--pad-v) var(--pad-h);
    position: relative;
  }

  /* 背景パターン */
  section::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: 
      radial-gradient(circle at 20% 80%, rgba(52, 152, 219, 0.03) 0%, transparent 50%),
      radial-gradient(circle at 80% 20%, rgba(231, 76, 60, 0.03) 0%, transparent 50%);
    pointer-events: none;
  }

  .wide-frame { 
    position: relative; 
    background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
    border-radius: 12px;
    box-shadow: 0 8px 32px rgba(0,0,0,0.1);
    margin: 20px 0;
  }

  .wide-frame::before,
  .wide-frame::after  {
    content: "";
    position: absolute;
    left: 0; right: 0;
    height: var(--border-h);
    background: linear-gradient(90deg, var(--color-accent) 0%, var(--color-secondary) 100%);
  }
  .wide-frame::before { top: 0; border-radius: 12px 12px 0 0; }
  .wide-frame::after  { bottom: 0; border-radius: 0 0 12px 12px; }

  h1, h2 { font-weight: 900; }
  h1 { 
    font-size: var(--fs-title); 
    background: linear-gradient(135deg, var(--color-accent), var(--color-secondary));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  h2 { 
    font-size: var(--fs-h2);
    color: var(--color-dark);
  }
  p, ul, ol { font-size: var(--fs-body); }

  .accent-line {
    display: inline-block;
    padding-bottom: 8px;
    border-bottom: 4px solid var(--color-accent);
    position: relative;
  }

  .accent-line::after {
    content: "";
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 30%;
    height: 4px;
    background: var(--color-secondary);
  }

  /* 表組みのスタイル強化 */
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 25px 0;
    font-size: 16pt;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    border-radius: 12px;
    overflow: hidden;
    background: white;
  }

  th, td {
    border: none;
    padding: 16px 20px;
    text-align: left;
    vertical-align: top;
  }

  th {
    background: linear-gradient(135deg, var(--color-accent), var(--color-secondary));
    color: white;
    font-weight: 700;
    font-size: 16pt;
    text-shadow: 0 1px 2px rgba(0,0,0,0.1);
  }

  td {
    font-size: 14pt;
    line-height: 1.5;
    border-bottom: 1px solid #e9ecef;
  }

  tr:nth-child(even) {
    background-color: #f8f9fa;
  }

  tr:hover {
    background-color: #e3f2fd;
    transform: translateY(-1px);
    transition: all 0.2s ease;
  }

  /* 箇条書きの調整 */
  ul, ol {
    margin: 20px 0;
    padding-left: 30px;
  }

  li {
    margin: 10px 0;
    line-height: 1.6;
    position: relative;
  }

  ul li::before {
    content: "▶";
    color: var(--color-accent);
    font-weight: bold;
    position: absolute;
    left: -20px;
  }

  /* 強調テキスト */
  strong {
    color: var(--color-accent);
    font-weight: 700;
    text-shadow: 0 1px 2px rgba(52, 152, 219, 0.1);
  }

  /* 金額表示の強調 */
  .price {
    font-size: 24pt;
    font-weight: 900;
    background: linear-gradient(135deg, var(--color-accent), var(--color-secondary));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    text-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }

  /* 体制図のスタイル */
  .org-chart {
    background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
    border: 2px solid var(--color-accent);
    border-radius: 12px;
    padding: 25px;
    margin: 25px 0;
    font-family: 'Courier New', monospace;
    font-size: 16pt;
    line-height: 1.8;
    box-shadow: 0 4px 20px rgba(52, 152, 219, 0.1);
    position: relative;
  }

  .org-chart::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: linear-gradient(90deg, var(--color-accent), var(--color-secondary));
    border-radius: 12px 12px 0 0;
  }

  /* カードスタイル */
  .card {
    background: white;
    border-radius: 12px;
    padding: 25px;
    margin: 20px 0;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    border-left: 4px solid var(--color-accent);
  }

  /* アイコン付きリスト */
  .icon-list li {
    padding-left: 40px;
    position: relative;
  }

  .icon-list li::before {
    content: "✓";
    position: absolute;
    left: 0;
    color: var(--color-accent);
    font-weight: bold;
    font-size: 18pt;
  }
---

<!-- _class: lead wide-frame -->

# <span class="accent-line">Dify 基盤保守運用提案</span>

## 鴻池運輸様向け Custom プラン

**株式会社アルゴマティック**
_2025 年 1 月 28 日_

---

<!-- _class: wide-frame -->

## <span class="accent-line">Agenda</span>

<div class="card">
<ul class="icon-list">
<li><strong>ご提案プラン詳細</strong></li>
<li><strong>構築スケジュールと体制</strong></li>
<li><strong>プロジェクト推進体制と費用</strong></li>
<li><strong>お見積もり前提条件</strong></li>
<li><strong>まとめと Next Action</strong></li>
</ul>
</div>

---

<!-- _class: wide-frame -->

## <span class="accent-line">ご提案プラン詳細</span>

### Custom プラン（鴻池運輸様専用）

| 項目                          | 詳細内容                                                                                                                                                                                                          |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **監視内容**                  | ・ユーザーからの障害発生報告のチケット管理<br>・アクセス数や CPU 利用率などのメトリクス監視<br>・アプリケーションログの収集/監査・エラーログの検知/アラート                                                       |
| **対応時間帯**                | 平日 9 時～ 18 時                                                                                                                                                                                                 |
| **インシデント時対応体制**    | **【一次・二次対応：オペレーター】**<br>・インシデント発生報告<br>・アプリケーションログ調査、原因の切り分け・推定<br><br>**【修正対応：インフラエンジニア】**<br>・原因特定後のプログラム/インフラ設定の修正作業 |
| **Dify バージョンアップ対応** | 半年に 1 回                                                                                                                                                                                                       |
| **AWS アップデート対応**      | 2 週間以内に対応                                                                                                                                                                                                  |

---

<!-- _class: wide-frame -->

## <span class="accent-line">費用詳細</span>

<div class="card">
<h3>初期費用：<span class="price">¥1,000,000</span></h3>

<ul class="icon-list">
<li>アプリケーションログ収集/監査・エラー検知/アラート基盤の構築</li>
<li>チケット管理システムの導入/設定・運用手順書の作成</li>
<li>継続的なアップデート基盤の構築</li>
</ul>
</div>

<div class="card">
<h3>月額費用：<span class="price">¥250,000</span></h3>

<ul class="icon-list">
<li><strong>運用保守費用（オペレーター）：¥125,000</strong></li>
<li><strong>修正対応費用（インフラエンジニア）：¥125,000</strong></li>
<li>※月 8 時間分の作業工数を含む</li>
</ul>
</div>

---

<!-- _class: wide-frame -->

## <span class="accent-line">構築スケジュールと体制</span>

### 体制別タスク分担

| 役割                     | 担当内容               | 期間             |
| ------------------------ | ---------------------- | ---------------- |
| **① 運用構築エンジニア** | 初期構築・監視基盤構築 | 7/21 週～ 8/4 週 |
| **② オペレーター**       | 1,2 次運用・ログ調査   | 8/5 週～継続     |
| **③ インフラエンジニア** | 各種対応・改修作業     | 随時対応         |

### スケジュール概要

<div class="card">
<ul class="icon-list">
<li><strong>7/21 週～ 7/28 週</strong>: 基盤構築フェーズ</li>
<li><strong>8/5 週～</strong>: 運用開始フェーズ</li>
<li><strong>継続</strong>: 監視・保守・対応</li>
</ul>
</div>

---

<!-- _class: wide-frame -->

## <span class="accent-line">プロジェクト推進体制</span>

### 体制図

<div class="org-chart">
プロジェクト責任者
├── ① 運用構築エンジニア（初期構築 担当）
├── ② 運用チーム（オペレーター）（一次・二次対応 担当）
└── ③ インフラエンジニア（障害修正・改修 担当）
</div>

### ご請求範囲

<div class="card">
上記 ①、②、③ の 3 者を包含
</div>

---

<!-- _class: wide-frame -->

## <span class="accent-line">お見積もり詳細</span>

### 期間：2025/07/01 - 2025/09/30

| 項目                       | 内容・役割                                                   | 元単価          | 値引き      | 適用単価      | 期間/数量        | 金額（税抜）   | 備考                                     |
| -------------------------- | ------------------------------------------------------------ | --------------- | ----------- | ------------- | ---------------- | -------------- | ---------------------------------------- |
| **初期費用**               | **① 運用構築エンジニア**<br>監視/アラート基盤構築 他         | 1,000,000 円/月 | -100,000 円 | 900,000 円/月 | 0.5 人月 ×2 ヶ月 | **900,000 円** | チケット管理システム環境共有による値引き |
| **月額費用**               | **② 運用保守（オペレーター）**<br>一次/二次対応、原因調査    | 160,000 円/月   | -35,000 円  | 125,000 円/月 | 3 ヶ月           | **375,000 円** | Custom プラン適用による値引き            |
|                            | **③ 修正対応（インフラエンジニア）**<br>原因特定後の修正作業 | 2,500,000 円/月 | ―           | 125,000 円/月 | 3 ヶ月           | **375,000 円** | 0.05 人月稼働（月 8 時間相当）           |
| **合計**                   |                                                              |                 |             |               |                  | **¥1,650,000** |                                          |
| **（参考）お値引き前合計** |                                                              |                 |             |               |                  | ¥1,855,000     |                                          |

---

<!-- _class: wide-frame -->

## <span class="accent-line">お見積もり前提条件</span>

### 本見積もりの保守対象範囲について

<div class="card">
<h4>重要：保守対象範囲の明確化</h4>

<ul class="icon-list">
<li>本見積もりにおける保守運用の対象範囲は、<strong>本番環境のみ</strong>といたします。</li>
<li>今後構築される<strong>検証環境およびステージング環境</strong>の保守運用は本契約の範囲外とし、対応が必要な場合は別途協議の上、ご提案させていただきます。</li>
</ul>
</div>

### 対象外システム

<div class="card">
以下のシステムは本保守運用の直接の対象範囲外となります：

<ul class="icon-list">
<li>Google Cloud Platform (Vertex AI)</li>
<li>Perplexity API</li>
<li>Okta</li>
</ul>
</div>

### その他の前提条件

<div class="card">
<ul class="icon-list">
<li>契約期間：2025 年 7 月 1 日～ 2025 年 9 月 30 日</li>
<li>対応時間：平日 9 時～ 18 時</li>
<li>緊急時対応：別途協議</li>
</ul>
</div>

---

<!-- _class: wide-frame -->

## <span class="accent-line">まとめ & Next Action</span>

### 🎯 重要なポイント

<div class="card">
<ul class="icon-list">
<li><strong>Custom プラン</strong>による最適化された保守運用</li>
<li><strong>明確な役割分担</strong>と<strong>費用内訳</strong>の提示</li>
<li><strong>保守対象範囲</strong>の明確化による認識齟齬防止</li>
</ul>
</div>

### 🚀 今すぐ始められること

<div class="card">
<ol class="icon-list">
<li><strong>ご提案内容のご検討</strong></li>
<li><strong>体制・スケジュールのご確認</strong></li>
<li><strong>契約条件の詳細協議</strong></li>
</ol>
</div>

### 💡 お問い合わせ

<div class="card">
ご不明な点がございましたら、お気軽にお声がけください。

<strong>株式会社アルゴマティック</strong>

</div>

_最終更新: 2025-01-28 15:45:00 JST_
