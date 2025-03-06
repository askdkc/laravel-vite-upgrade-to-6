# LaravelでViteを6に更新する時の注意点

## What's this? これは何？
Laravelのパッケージのバージョンアップを進めてて、GitHub ActionのCIテストでViteがコケるな〜、と思った人はここを見直そう

### `package.json`に`"type": "module"`を追加

- `package.json`の先頭のここを<br>
  ↓
```json
  "private": true,
  "scripts": {
     "dev": "vite",
     "build": "vite build"
  },
```

- ↓こうする
```json
  "private": true,
  "type": "module",
  "scripts": {
     "dev": "vite",
     "build": "vite build"
  },
```


### `postcss.config.js`ファイルがある場合は名前を変更する
 - `postcss.config.js` を使っている場合は、ファイル名を `postcss.config.cjs` にする
