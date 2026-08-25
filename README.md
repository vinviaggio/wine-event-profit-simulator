# ワインイベント採算シミュレータ

## 概要

ワインイベントについて、参加人数・ワイン銘柄数・第1部実消費率・第2部提供量・平均希望小売価格・仕入率・追加開栓本数などを変更しながら、

- CASE A「理論・保守モデル」
- CASE B「実運用・手動設定シナリオ」

の採算性とワイン提供量を比較するためのインタラクティブシミュレーター。

現在は D'Argento Croce での「第1部 試飲会＋第2部 ペアリングワイン会」を基準モデルとして実装している。ただし Repository 自体は、将来ほかのワインイベントにも利用する汎用シミュレーターとして管理する。

単一HTML＋JavaScript（フレームワーク・ビルド環境なし）の静的Webアプリ。外部CDN（Tailwind CSS / Chart.js / FontAwesome / Google Fonts）を使用している。

## 利用方法

GitHub Pages URL をブラウザで開いて使用する。

https://&lt;GitHubユーザー名&gt;.github.io/wine-event-profit-simulator/

PC・スマートフォンの通常ブラウザで動作する。AIツール（Gemini / Claude 等）を開く必要はない。

## Source of Truth

- この GitHub Repository の main branch をソースコードの正本とする。
- `docs/simulator-spec.md` を仕様の正本とする。
- Google Drive 上の「ワインイベント採算シミュレータ」は GitHub 移行後はバックアップ扱いであり、正本ではない。

## 更新ルール

変更前:

1. Fetch / Pull して main を最新状態にする。

変更後:

1. Commit
2. Push

重要変更時:

- `CHANGELOG.md` を更新する（簡易 Semantic Versioning: v1.0.1 = 軽微な修正 / v1.1.0 = 機能追加 / v2.0.0 = 大規模仕様変更）。

AI（Claude / ChatGPT 等）に修正を依頼するときのルール:

> まず最新 main と `docs/simulator-spec.md` を確認し、既存仕様を壊さず変更すること。

## Git運用

- main = 常に利用可能な安定版。
- 通常の軽微な修正では複雑な branch 運用は不要（main に直接 commit / push）。
- 計算ロジック変更や大きな機能追加の場合のみ `feature/xxxx` branch を作成し、動作確認後 main へ merge する。

## Future Improvements（今回は未実装・将来候補）

以下は現時点では実装しない。GitHub Issue 候補として記録のみ。

- localStorage による設定保存
- 複数シナリオ保存
- イベント名／開催日管理
- 実績値保存
- CSV出力
- PDF出力
- シナリオ比較
- スマートフォンUI改善
- 複数レストラン対応
- イベント形式別テンプレート
- D'Argento Croce 以外への汎用化
