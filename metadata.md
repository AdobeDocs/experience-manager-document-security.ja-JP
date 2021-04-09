---
cloud: Experience Cloud
feature-set: Experience Manager Forms
mini-toc-levels: 2
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-document-security.ja-JP
index: true
translation-type: ht
source-git-commit: 7be2b17e7685a391dcccde2cc008802b5773cadf
workflow-type: ht
source-wordcount: '130'
ht-degree: 100%

---


# 内部使用メタデータ

metadata.md ファイルには、リポジトリー内にあるユーザーガイドの TOC.md ファイルにパススルーされるリポジトリーレベルのメタデータが含まれています。任意のユーザーガイドの metadata.md コンテンツを変更するには、任意の TOC.md ファイル内でそのように処理してください。

| メタデータ | 動作 |
|--- |--- |
| solution-title | 記事ヘッダーでリンクとして使用されます。 |
| solution-hub-url | helpx ハブページを開きます。 |
| solution-icon | ソリューションタイトルの横にソリューションアイコンを表示します。まだ実装されていません。 |
| getting-started-url | helpx の「はじめに」のページへのリンク |
| tutorials-url | ビデオチュートリアル（helpx チュートリアルまたは KT チュートリアル）へのリンク |
| mini-toc-levels | 右側のレールに表示される見出しレベルの数を決定します。デフォルトは 2 です。 |
| git-repo | 内部使用のマスターリポジトリーの場所を指定します。 |

TOC.md ファイル内

| メタデータ | 動作 |
|--- |--- |
| user-guide-title | 記事ヘッダーでリンクとして使用されます。 |
| user-guide-url | helpx ハブページを開きます。 |
