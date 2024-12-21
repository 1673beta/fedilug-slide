---
marp: true
title: Misskey用外付けCLIを作っている話
paginate: true
author: Esurio
theme: gaia
---

<!-- _class: lead-->
# Misskey用外付けCLIを作っている話
Esurio(@esurio1673@c.koliosky.com)

---

# 自己紹介

名前: Esurio
SNS: @esurio1673@c.koliosky.com
ディストリ: Fedora
言語: Typescript, Rust
普段: CherryPick(Misskeyのフォーク)をフォークしてる
ソフトウェア: CherryPick, Akkoma, GoToSocial, Mitra, Hollo

---

## notectlとは
Misskey版tootctl的な管理用CLIツール
misskey-devとは何も関係がない非公式の外付けツール

---

## 経緯
Misskeyにはtootctlのように管理用のCLIツールがない  
→これが一因としてMisskeyは長期運用に向かないなどと言われることがある  
→tootctl、なんか色々できるっぽくて羨ましい！
  →じゃあ作るか、外付けで

---

## 技術スタック

#### 言語
Rust, Dockerfile
#### ライブラリ
clap(CLIパーサー)
SeaORM(ORM)
inkjet(装飾)
tokio(非同期)
meilisearch-sdk(MeilisearchのSDK)

---

## Rustにした理由
- 実行速度が速く、軽い
- 私好みの書きごこち
- 将来的に自フォークのバックエンドの一部をRustにする予定がある
- GoのORMがどれも合わなかった

---

## 開発中のやらかし
- `std::core::Result`を使いたかったのに誤って`std::fmt::Result`を選んで気づかない
- Rustの非同期では`.await`をつけて実行する必要があるが、つけ忘れた
- 所有権の借用・参照周り

---

## 今の課題
- CI/CDの整備
- devcontainerの整備
- ドキュメントの整備
- エラーハンドリングの改善
- ローカルに作用する機能をどうするか

---

## 今後実装したい機能
- 指定した日時以前のリモートの投稿を削除する機能
- objectid, meidの対応
- 指定した条件でリモートのアカウントをまとめて削除する機能
- Meilisearchに検索を再デプロイする機能
- FTTのキャッシュを削除・再構築する機能
- notectl/Misskeyのリポジトリに更新があるか確認する機能

---

<!-- _class: lead-->
## おしまい