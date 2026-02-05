# project-manager
デモ
https://claude.ai/public/artifacts/88469949-2ade-493e-830e-f1443221f499

📐 Codex用 要約プロンプト（MVP → フル機能）

あなたは熟練したフルスタックSaaSエンジニアです。
Backlogの構造化タスク管理 + Jootoのカンバン操作性 + ガント + 備品/予算管理を統合した
少人数向け日本語プロジェクト管理Webアプリを構築してください。

🎯 コンセプト

「今日は何をやるか」と「来月どうなるか」と「いくら使うか」が一瞬で分かる。

UIは Linear + Notion の中間。
白ベース / 余白多め / 小さめ角丸 / アイコン最小。

起動3秒以内。操作説明不要。

技術

React + TypeScript

Tailwind

Zustand

Supabase or Firebase

ガントは軽量自作 or lightweight lib

認証：Emailのみ

Netlify deploy前提

最初は：

プロジェクト1つ

ユーザー固定

🧩 データ構造
Project

id, name, budget

Task

id
projectId
title
description
status(todo/doing/review/done)
assignee
startDate
dueDate
label
priority
createdAt

subTasks[]
comments[]
activityLog[]

Member

id
name
email
role(admin/member/viewer)

PurchaseItem（備品）

id
name
unitPrice
quantity
total
url
memo
category
status(申請/承認/発注/購入済)
priority
assignee
paymentMethod
receiptUrl
deliveryDate
repeatFlag

🖥 画面
A カンバン（メイン）

todo / doing / review / done

D&D

カード表示：

タイトル

担当

期限

ラベル

進捗バー

フィルタ：

担当

期限

ラベル

検索

B ガント（必須）

横：日付（週/月切替）

縦：タスク

start〜due をバー表示

ドラッグで期間変更

今日ライン

ステータス色連動

担当者レーン切替

C ダッシュボード

全タスク数

自分のタスク

期限切れ

完了率

今日の予定

D 設定画面（必須）
メンバー管理

追加/削除

名前/メール/権限

通知

担当追加

期限変更

コメント

ステータス変更

通知先メール

プロジェクト

名前

ステータス列

ラベル管理
✏ タスク編集モーダル

タイトル

説明

担当

開始日

期限

ラベル

優先度

サブタスク

コメント

💬 コラボ系

コメント

@メンション

アクティビティログ（誰が何した）

📦 備品・購入管理（超重要）
基本

単価

個数

合計自動計算

URL

備考

購入済フラグ

追加（全部実装）

カテゴリ

承認フロー

納品予定

領収書URL

購入担当者

優先度

支払い方法

CSV export

予算アラート(80%)

再発注

💰 予算

プロジェクト総予算

使用済（購入済のみ）

申請中

残額

使用率バー

カテゴリ別予算

購入済のみ残額に反映。

ゴール

カンバン + ガント + 備品 + 予算が一体化

「作業」と「金」が同じ画面で見える

ローカル保存 → Supabase移行想定

必要に応じて：

DB schema

API設計

UIワイヤー

コンポーネント分割

も提示してください。
