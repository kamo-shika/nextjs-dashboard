# チュートリアルを進めたときのメモ

## 基本方針

- [Next.js のチュートリアル](https://nextjs.org/learn)を進めてみる
- ドキュメントは英語だけど、慣れも兼ねてなるべく翻訳せずに進める
- 気になったところはメモしておく

## メモ

### `pnpm i`で警告が出る

チュートリアル通りに実施してみたところ、下記の警告が出ました。

```bash
╭ Warning ───────────────────────────────────────────────────────────────────────────────────╮
│                                                                                            │
│   Ignored build scripts: bcrypt, sharp.                                                    │
│   Run "pnpm approve-builds" to pick which dependencies should be allowed to run scripts.   │
│                                                                                            │
╰────────────────────────────────────────────────────────────────────────────────────────────╯
```

あとで調べとこ。

### テンション上げたくて画像を勝手に貼る

TOPページの左側が空いてる（多分後のチャプターでやる）ので、画像を貼ってみた。

```typescript
import Image from 'next/image';

<Image
src="/TURN_VISUAL_FINAL_Re.jpg"
width={1000}
height={760}
className="hidden md:block"
alt="サカナクション"
/>
```

サカナクション最高！！

※1. `Image`コンポーネントを使う時は`next/image`をインポートする必要あり。  
※2. コンポーネントなくて、`JSX element class does not support attributes because it does not have a 'props' property.`というエラーが出た。

### クイズに間違える

下記のクイズの回答を間違えた。。。  
「CSSモジュールは、各コンポーネントに固有のクラス名を作成するので、スタイルの衝突を心配する必要はありません。」とのこと。（翻訳使った。）

> Q. What is one benefit of using CSS modules?
> A. Provide a way to make CSS classes locally scoped to components by default, reducing the risk of styling conflicts.

### bcrypt でビルドエラー

```bash
 Collecting page data  ...[Error: Cannot find module '...\nextjs-dashboard\node_modules\.pnpm\bcrypt@5.1.1\node_modules\bcrypt\lib\binding\napi-v3\bcrypt_lib.node
```

チュートリアルのコードは`bcrypt`を使っていたが、`bcryptjs`に変更したらエラーが出なくなった。

[bcryptjs](https://www.npmjs.com/package/bcryptjs)
