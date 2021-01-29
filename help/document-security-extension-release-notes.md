---
title: AEM Document Security for Microsoft Office - リリースノート
description: AEM Document Security 6.2 Extension for Microsoft Office をインストールする前に、リリースノートをお読みください。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
translation-type: tm+mt
source-git-commit: 403b800eab086d131beb65a496836158778954ee
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 79%

---


# AEM Document Security for Microsoft Office - リリースノート{#aem-document-security-for-microsoft-office-release-notes}

## AEM Document Security for Microsoft Office の新機能 {#whats-new-in-aem-document-security-for-microsoft-office}

* **Office 2019 に対応：** Document Security Extension for Microsoft Office では、Microsoft Office 2019 へのサポートが追加されました。Office 365 の一部としてインストールされた Microsoft Office 2019 デスクトップ用アプリケーションでも動作すると想定されます。

>[!NOTE]
>
>この記事では、「Adobe Experience Manager Document Security for Microsoft Office」、「Adobe Experience Manager Document Security Extension for Microsoft Office」、および「Document Security Extension for Microsoft Office」の各用語を同じ意味で使用します。

## AEM Document Security Extension for Microsoft Office のインストールと設定 {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

本バージョンの Document Security Extension for Microsoft Office は、Adobe LiveCycle Rights Management ES2 以降、および AEM Forms 向け Document Security アドオンと互換性があります。

AEM Document Security Extension for Microsoft Office をインストールする前に、本書の情報をお読みください。詳細なインストール手順については、[『 AEM Document Security Extension for Microsoft Office のインストールと設定方法』](installing-configuring-aemdsext.md)の記事を参照してください。

## 修正された問題  {#fixed-issues}

* 文字列が縦に表示されて、改行が誤った位置に追加されます。(参照番号 CQ-4201054)

## 既知の問題 {#known-issues}

### サードパーティ製プラグインはサポートされていません{#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office はサードパーティ製プラグインと一緒には機能しません。Document Security Extension for Microsoft Office をインストールする前に、Microsoft Office 用のサードパーティ製プラグインをすべてアンインストールしてください。

### Microsoft Word、Excel、および PowerPoint で無効になるメニューオプション  {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office は組み込みの保護機能を使用して、ドキュメント、ワークシート、およびプレゼンテーションを保護します。 この操作により、Excel、Word、および PowerPoint のメニューオプションの一部が無効になります。

### Microsoft Office 2013、2016 および 2019 における制限  {#restrictions-for-microsoft-office}

Microsoft Office で保護セッションを使用している間は、次のオプションが使用できません。

* Microsoft Office 2016 または Microsoft Office 2019

   * ファイル／名前を付けて保存
   * ファイル／履歴
   * ファイル／共有
   * ファイル／書き出し
   * ファイル／発行
   * ファイル／アカウント
   * ファイル > 情報 > 文書の保護／ワークブック／プレゼンテーション > パスワードによる暗号化
   * ファイル／情報／文書の保護／デジタル署名の追加
   * ファイル／情報／文書の保護／最終版にする
   * 右上の共有オプション

* Microsoft Office 2013

   * ファイル／名前を付けて保存
   * ファイル／共有
   * ファイル／書き出し
   * ファイル／アカウント
   * ファイル > 情報 > 文書の保護／ワークブック／プレゼンテーション > パスワードによる暗号化
   * ファイル／情報／文書の保護／デジタル署名の追加
   * ファイル／情報／文書の保護／最終版にする

### SharePoint Server から保護されたドキュメントを開く  {#opening-a-protected-document-from-sharepoint-server}

保護されたドキュメントを開く：SharePoint ServerからMicrosoft Office用ドキュメントセキュリティ拡張機能で保護されたドキュメントを開こうとすると、Microsoft Word、Microsoft Excel、Microsoft PowerPointなどのファイルの種類に関連付けられたMicrosoft Officeプログラムが開かれない場合があります。 該当するプラグインをインストールしたことを示すエラーメッセージが表示されます。 したがって、SharePoint ServerからMicrosoft Office用ドキュメントセキュリティ拡張機能で保護されたドキュメントを開く前に、関連付けられたMicrosoft Officeプログラムを開くことをお勧めします。

（オプション）SharePoint Serverからドキュメントセキュリティ拡張機能(Microsoft Office)の保護されたドキュメントを開く前に、キャッシュフォルダをクリアすることをお勧めします。

保護されたドキュメントを SharePoint Server から開くと、適用されたポリシーに関係なく、ドキュメントのすべての権限が無効になります。

### プリンターがインストールされていない場合に、Excel 2013、2016、2019 ファイルに対して動的透かしのポリシーを適用する  {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

プリンターがインストールされていないコンピューターで動的透かし付きのポリシーを Excel 2013、2016 または 2019 ファイルに適用し、そのファイルを保存すると、「Internal error while applying dynamic watermark」というエラーが発生します。このエラーは、保護されたファイルを再度開いたときにも表示されます。 透かしは適用されず、表示/ページレイアウトにも表示されません。

### サポートされている Office アプリケーションで Windows データ実行防止機能を無効にする  {#disable-windows-data-execution-prevention-for-supported-office-applications}

Document Security Extension for Microsoft Office を使用するときは、Windows データ実行防止（DEP）機能を無効にすることをお勧めします。

### 共有されたMicrosoft Officeファイルは、ドキュメントセキュリティ拡張機能{#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}を使用して保護できません

ドキュメントセキュリティ拡張機能を使用して共有されたMicrosoft Officeファイルを保護すると、エラーが発生し、共有ファイルは保護されません。

### Document Security Extension for Microsoft Office および McAfee VirusScan がインストールされている PC 上で Office アプリケーションを起動する {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Document Security がインストールされ、McAfee VirusScan の On-Access Scan 機能が有効なコンピュータで Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console の「Buffer Overflow Protection」オプションを無効にしてください。

### サポートされていない Microsoft Office 言語がインストールされている PC に Document Security Extension for Microsoft Office をインストールする  {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

サポートされていない言語の Microsoft Office アプリケーションがインストールされている PC にDocument Security Extension for Microsoft Office をインストールする際は、事前に Office アプリケーションを少なくとも 1 回は起動してください。

### ユーザーがオフラインアクセス権限を持っていない場合でも、「オフライン同期」ボタンが有効になる  {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

ユーザーがそのファイルに対してオフラインアクセス権限を持っていない場合でも、「オフライン同期」ボタンが有効になります。ただし、ボタンを選択しても何も実行されません。

### Microsoft Officeの体験版はサポート対象外 {#no-support-for-trial-versions-of-microsoft-office}

AEM Document Security Extension for Microsoft Office は体験版の Microsoft Office をサポートしていません。拡張機能をインストールする前に、Microsoft Officeのライセンスを取得したコピーがインストールされ、ライセンス認証が行われていることを確認してください。

### 保護されたMicrosoft Officeファイル{#unable-to-open-a-protected-microsoft-office-files}を開けません

Microsoft Office の保護ビューが有効の場合、Right  Management Extension は保護された Microsoft Excel ファイル (XLS、XLSX) および保護された Microsoft PowerPoint (PPT) ファイルをリモート場所から開くことができません。

### 画像または背景色を含むMicrosoft Excelドキュメントのセルが、透かしの上に表示されます{#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Microsoft Excel 文書のセルに画像が含まれているか、または背景色で塗りつぶされていて、動的透かしポリシーが文書に適用されている場合、セルに埋め込まれた画像や背景色が透かしの上に表示され、透かしが覆われます。

### 複数の証明書での利便性の問題 {#usability-issue-with-multiple-certificates}

クライアントマシン上の複数の証明書が存在し、ユーザーが証明書選択ダイアログをキャンセルすると、このダイアログが再び表示され、ユーザーはダイアログを 2 回キャンセルすることになります。

### Microsoft PowerPoint では保護されたドキュメントを編集できる  {#microsoft-powerpoint-allows-editing-protected-documents}

保護された文書を Microsoft PowerPoint 上で編集しようとすると、「この文書を変更することはできません。変更を保存することはできません」とのメッセージが表示されます。しかし、メッセージを閉じた後も、引き続きテキストの追加や編集を行うことができます。ただし保護された文書に対する変更は保存されません。

上記の動作は、PowerPoint 2013、PowerPoint 2016、および PowerPoint 2019 で発生します。
