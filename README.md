# ouchi-colon-korokoro-race
MIKAROとMooloが登場するOuchi Colonのころころレースゲーム試作版

## GitHub更新手順（反映されないとき）

### 0) 初回だけ: リモート設定（`git push` でエラーが出る場合）
```bash
git remote -v
git remote add origin https://github.com/<ユーザー名>/ouchi-colon-korokoro-race.git
# すでに origin がある場合はURL更新
git remote set-url origin https://github.com/<ユーザー名>/ouchi-colon-korokoro-race.git
```

### 1) ローカルで変更をコミット
```bash
git add .
git commit -m "Update game assets"
```

### 2) GitHubへプッシュ
```bash
git push origin main
```

### 3) GitHub Pages設定を確認
1. GitHubリポジトリの **Settings** を開く  
2. 左メニュー **Pages** を開く  
3. **Build and deployment** で以下を設定
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/ (root)`
4. Save後、数分待って公開URLを確認

### 4) それでも更新されない場合
- ブラウザのスーパーリロード（Windows: `Ctrl+F5`, Mac: `Cmd+Shift+R`）
- CDNキャッシュ対策で `index.html?v=2` のようにクエリを付けて確認
- Actions タブでデプロイ失敗ログを確認

## PNGアセット対応
以下のPNGを `assets/` フォルダに配置すると、図形描画の代わりにスプライト表示されます。

- `assets/bg_living_room_race.png`
- `assets/mikaro_back.png`
- `assets/moolo_enemy.png`
- `assets/block_red.png`
- `assets/block_blue.png`

画像が未配置または読み込み失敗時は、既存のCanvas図形フォールバックでゲームは動作します。

## オープニング画面画像（添付2枚目）
添付2枚目のようなオープニング画像を使う場合は、以下のファイル名で配置してください。

- `assets/opening_title.png`

`title` 画面でこの画像が見つかれば全画面表示され、無い場合は従来の描画画面が表示されます。


### assetsフォルダがない場合
`assets/` が存在しない場合は作成してください（例: `assets/.gitkeep` を置いて管理）。
