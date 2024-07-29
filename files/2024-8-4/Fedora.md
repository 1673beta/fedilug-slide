---
marp: true
title: MacbookにFedoraを入れてFedi鯖を動かす
paginate: true
author: Esurio
theme: gaia
---

<!-- _class: lead-->

# MacbookにFedoraを入れてMisskeyを動かす
Esurio(@esurio1673@c.koliosky.com)

---

# 自己紹介

```json
{
    "name": "Esurio",
    "account": "@esurio1673@c.koliosky.com",
    "jobs": "student",
    "distribution": "Ubuntu, Debian, Fedora",
}
```

---

# 背景

* 元々Windows機で開発とかしていた

* Windows機だと以下の問題点がある
    1. nodeのバージョン管理にnが使えない
    2. 物理的に重くて持ち運びが不便
    3. Windowsノートのバッテリー持ちが悪い

→ M2 Macbook Airを買う(ローン返済中)

---

# 買ってわかったMacの問題点

* **メモリが足りない**
    * devcontainer動かすとそれだけでメモリ使用量が13GBいく

* Unix系なのに中途半端
    * 公式のパッケージマネージャーがない

→ じゃあLinux入れるか

---

# Asahi Linuxとは

![bg fit left:30% 30%](./assets/AsahiLinux_logomark.svg)

Apple Sillicon MacにLinuxを移植するプロジェクト&コミュニティ  
  
名前の由来は旭というりんごの品種  
  
  ![w:36px](./assets/mastodon-logo-purple.svg)
  @AsahiLinux@social.treehouse.systems
  
---

# インストール方法

### 必要なもの
* 対応しているMac
* 最悪macOSを吹き飛ばす度胸

### インストール
macOSでターミナル開いてコマンドを叩くだけ！

```bash
curl https://alx.sh | sh
```

---

# Asahi Linuxの問題点
 1. USB-Cポートが使えない
    * 外部ディスプレイも使えない
 2. 公式だとFedoraしかない
    * 非公式だとUbuntu Asahiがある
 3. M3対応してない

---

# Misskeyを動かす
手癖で動かせるのでとりあえずMisskey
  
* 普通のaarch64で動くFedoraなのでDocker Composeでぽん！

---

# 実際にサーバー運用する場合

* インストール時にKDE Plasma、GNOME、Fedora Serverから選べる
* Mac miniかMac studioなら良さそう

---

# おわり

楽しい！！！！！
あとTimemachineでバックアップは取ろう！！！！！