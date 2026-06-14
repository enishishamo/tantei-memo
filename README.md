# たんていメモ（Q1 もうちょうえん）

JIBUN CHOICE 病院版（豊地病院）B1 タスク。小3〜4の子どもがタブレットで研修医として
患者を診て、問診→聴診→心エコー→CT で5つの病気を絞り、虫垂炎（もうちょうえん）を
見つけて治す、1ファイル完結の Web アプリ（HTML/CSS/JS）。

## 使い方
`index.html` をブラウザで開くだけ。ビルド不要。

ローカルで配信したい場合:
```
python3 -m http.server 8123
# → http://localhost:8123
```

## 6ステップ
1. 臓器マップ（5人の容疑者紹介）
2. 問診（ROS 8問・鑑別バー）
3. 聴診（胃腸炎を除外）
4. 心エコー（心筋梗塞を除外）
5. CT（胆のう→尿管→虫垂の順に確認・★メイン）
6. 説明→手術→感謝

## 画像（`img/`）
画像が無くても SVG フォールバックで全ステップ動く。`img/` に下記を置くと
リロードだけで本番絵に差し替わる（コード変更不要）:

- `figure_body.png`（正面図）
- `ct_01_lungs_heart.png` 〜 `ct_08_bladder.png`（CT 8枚）
- `zoom_gall_normal.png` / `zoom_gall_stone.png`
- `zoom_ureter_normal.png` / `zoom_ureter_stone.png`
- `zoom_appendix_inflamed.png`

> CT スライス6（虫垂）は「足元から見上げた輪切り＝画像の左下＝患者のみぎ下」に
> 配置すること（仕様書 付録プロンプトの "LOWER-LEFT" 準拠）。
