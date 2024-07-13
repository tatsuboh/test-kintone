# Kintone TypeScript 開発環境構築手順

## 1. プロジェクトディレクトリの作成

まず、新しいプロジェクトディレクトリを作成し、そこに移動します。

```sh
mkdir kintone-typescript-project
cd kintone-typescript-project
```

## 2. Node.js と npm のインストール確認

Node.js と npm がインストールされていることを確認します。

```sh
node -v
npm -v
```

インストールされていない場合は、[Node.js の公式サイト](https://nodejs.org/)からインストールしてください。

## 3. npm プロジェクトの初期化

npm プロジェクトを初期化します。

```sh
npm init -y
```

## 4. TypeScript のインストール

TypeScript と必要な型定義ファイルをインストールします。

```sh
npm install typescript @types/node --save-dev
```

## 5. TypeScript 設定ファイルの作成

TypeScript の設定ファイル `tsconfig.json` を作成します。

```sh
npx tsc --init
```

`tsconfig.json` を以下のように編集します。

```json
{
  "compilerOptions": {
    "target": "ES5",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src/**/*"]
}
```

## 6. ディレクトリ構造の作成

ソースコードを格納するディレクトリを作成します。

```sh
mkdir src
```

## 7. サンプル TypeScript ファイルの作成

`src/index.ts` というファイルを作成し、サンプルコードを書きます。

```ts
console.log('Hello, Kintone with TypeScript!')
```

## 8. TypeScript のビルド

TypeScript コードをコンパイルして JavaScript に変換します。

```sh
npx tsc
```

これで、`dist` フォルダにコンパイルされた JavaScript ファイルが生成されます。

## 9. `.gitignore` の設定

Git で管理しないファイルやディレクトリを指定するために、`.gitignore` ファイルを作成します。

```sh
touch .gitignore
```

以下の内容を `.gitignore` ファイルに追加します。

```
# Dependencies
node_modules/

# Compiled JavaScript files
dist/

# Logs
*.log

# TypeScript build info
*.tsbuildinfo
```

## 10. 初期コミットとプッシュ

プロジェクトの初期設定を GitHub リポジトリにコミットし、プッシュします。

```sh
git add .
git commit -m "Initial setup for Kintone TypeScript project"
git push origin main
```

以上で、Kintone で TypeScript を使った開発環境が整いました。`src` フォルダ内で TypeScript ファイルを作成・編集し、`npx tsc` コマンドでビルドして Kintone にアップロードする準備ができます。
