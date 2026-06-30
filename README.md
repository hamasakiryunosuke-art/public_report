# アンケート集計結果 公開ページ

## 仕組み

```
アンケート集計ツールv21.html（職員用）
  ↓ 「集計JSONをエクスポート」ボタン
  ↓ result.json をダウンロード
  ↓ このリポジトリにアップロード

index.html（このファイル）
  ↓ result.json を fetch して描画
  ↓ GitHub Pages で公開
  ↓ STUDIOページに iframe で埋め込み
```

## ファイル構成

| ファイル | 役割 |
|---|---|
| `index.html` | 集計結果の描画ページ（固定・更新不要） |
| `result.json` | 集計データ（調査ごとに差し替え） |

## データ更新手順

1. 職員PCで `アンケート集計ツールv21.html` を開く
2. layoutファイル・rawdataファイルを読み込んで集計
3. 「**集計JSONをエクスポート**」ボタンをクリック → `result.json` がダウンロードされる
4. GitHubのこのリポジトリを開く
5. `result.json` をドラッグ＆ドロップしてアップロード（「Commit changes」で確定）
6. 1〜2分後に公開ページへ自動反映

## STUDIOへの埋め込み

STUDIOの Embed ボックスに以下を貼り付ける：

```html
<iframe
  src="https://【GitHubユーザー名】.github.io/【リポジトリ名】/"
  width="100%"
  height="800"
  frameborder="0"
  style="border:none;">
</iframe>
```

## GitHub Pages の有効化手順

1. GitHubリポジトリの「Settings」→「Pages」
2. Source: `Deploy from a branch`
3. Branch: `main` / `/(root)`
4. 「Save」→ 数分後に `https://【ユーザー名】.github.io/【リポジトリ名】/` で公開
