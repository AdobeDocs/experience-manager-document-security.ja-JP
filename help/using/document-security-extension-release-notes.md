---
title: AEM Document Security for Microsoft Office - リリースノート
description: AEM Document Security 6.2 Extension for Microsoft Office をインストールする前に、リリースノートをお読みください。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 73%

---

# AEM Document Security for Microsoft Office - リリースノート{#aem-document-security-for-microsoft-office-release-notes}

## AEM Document Security for Microsoft Office の新機能 {#whats-new-in-aem-document-security-for-microsoft-office}

* **Office 2019 に対応：** Document Security Extension for Microsoft Office では、Microsoft Office 2019 へのサポートが追加されました。Office 365 の一部としてインストールされた Microsoft Office 2019 デスクトップ用アプリケーションでも動作すると想定されます。

>[!NOTE]
>
>このドキュメントでは、次の用語が互換的に使用されています。
>
>* Microsoft Office 用Adobe Experience Manager Document Security
>* Adobe Experience Manager Document Security Extension for Microsoft Office
>* Microsoft Office 用 Document Security 拡張機能

## AEM Document Security Extension for Microsoft Office のインストールと設定 {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

本バージョンの Document Security Extension for Microsoft Office は、Adobe LiveCycle Rights Management ES2 以降、および AEM Forms 向け Document Security アドオンと互換性があります。

AEM Document Security Extension for Microsoft Office をインストールする前に、本書の情報をお読みください。インストール手順について詳しくは、[AEM Document Security Extension for Microsoft Office のインストールと設定 ](installing-configuring-aemdsext.md) を参照してください。

## 修正された問題 {#fixed-issues}

* 文字列が縦に表示されて、改行が誤った位置に追加される。（CQ-4201054）

## 既知の問題 {#known-issues}

### サードパーティ製プラグインがサポートされていない {#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office はサードパーティ製プラグインと一緒には機能しません。Document Security Extension for Microsoft Office をインストールする前に、Microsoft Office 用のサードパーティ製プラグインをすべてアンインストールしてください。

### Microsoft Word、Excel、および PowerPoint でメニューオプションが無効になる {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office は組み込みの保護機能を使用して、ドキュメント、ワークシート、およびプレゼンテーションを保護します。この操作により、Excel、Word、および PowerPoint のメニューオプションの一部が無効になります。

### Microsoft Office 2013、2016 および 2019 における制限 {#restrictions-for-microsoft-office}

Microsoft Office で保護セッションを使用している間は、次のオプションが使用できません。

* Microsoft Office 2016 または Microsoft Office 2019

   * ファイル／名前を付けて保存
   * ファイル／履歴
   * ファイル／共有
   * ファイル／書き出し
   * ファイル／公開
   * ファイル／アカウント
   * ファイル ／情報／文書の保護／ワークブック／プレゼンテーション／パスワードによる暗号化
   * ファイル／情報／文書の保護／デジタル署名の追加
   * ファイル／情報／文書の保護／最終版にする
   * 右上の共有オプション

* Microsoft Office 2013

   * ファイル／名前を付けて保存
   * ファイル／共有
   * ファイル／書き出し
   * ファイル／アカウント
   * ファイル ／情報／文書の保護／ワークブック／プレゼンテーション／パスワードによる暗号化
   * ファイル／情報／文書の保護／デジタル署名の追加
   * ファイル／情報／文書の保護／最終版にする

### 保護されたドキュメントを SharePoint Server から開けない {#opening-a-protected-document-from-sharepoint-server}

保護されたドキュメントをSharePoint Server からMicrosoft Office 用 Document Security 拡張機能で開くには、まず、関連するMicrosoft Office プログラム（Word、Excel または PowerPoint）を開きます。開くと、ドキュメントが開かないことがあります。 該当するプラグインをインストールする必要があることを示すエラーメッセージが表示されます。したがって、Document Security Extension for Microsoft Office で保護されたドキュメントを SharePoint Server から開く前に、関連付けられている Microsoft Office プログラムを開くことをお勧めします。

（オプション）Document Security Extension for Microsoft Office で保護されたドキュメントを SharePoint Server から開く前に、キャッシュフォルダーを空にすることをお勧めします。

保護されたドキュメントを SharePoint Server から開くと、適用されたポリシーに関係なく、ドキュメントのすべての権限が無効になります。

### プリンターがインストールされていない場合に、Excel 2013、2016、2019 ファイルに対して動的な透かしのポリシーを適用する {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

プリンターがインストールされていないコンピューターで動的透かしを含むポリシーを Excel 2013、2016、2019 ファイルに適用すると、「動的透かしを適用する際に内部エラーが発生しました」というエラーが発生します。 このエラーは、保護ファイルを再度開くときにも表示されます。透かしは適用されず、表示／ページレイアウトにも表示されません。

### サポートされている Office アプリケーションで Windows データ実行防止機能を無効にする {#disable-windows-data-execution-prevention-for-supported-office-applications}

Document Security Extension for Microsoft Office を使用するときは、Windows データ実行防止（DEP）機能を無効にすることをお勧めします。

### 共有中の Microsoft Office ファイルは Document Security Extension を使用して保護できない {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

共有中の Microsoft Office ファイルを Document Security Extension を使用して保護すると、エラーが発生し、共有ファイルが保護されません。

### Document Security Extension for Microsoft Office および McAfee VirusScan がインストールされている PC 上で Office アプリケーションを起動する {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Document Security および McAfee VirusScan （On-Access Scan を有効にする）をインストールしたコンピューターで Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console で [Buffer Overflow Protection] オプションを無効にします。

### サポートされていない Microsoft Office 言語がインストールされている PC に Document Security Extension for Microsoft Office をインストールする {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

サポートされていない言語の Microsoft Office アプリケーションがインストールされている PC にDocument Security Extension for Microsoft Office をインストールする際は、事前に Office アプリケーションを少なくとも 1 回は起動してください。

### ユーザーがオフラインアクセス権限を持っていない場合でも、「オフライン同期」ボタンが有効になる {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

ユーザーがそのファイルに対してオフラインアクセス権限を持っていない場合でも、「オフライン同期」ボタンが有効になります。ただし、ボタンを選択しても何も実行されません。

### Microsoft Officeの体験版はサポート対象外 {#no-support-for-trial-versions-of-microsoft-office}

Document Security Extension for Microsoft Office は、Microsoft Office のトレイルバージョンをサポートしていません。 拡張機能をインストールする前に、Microsoft Office のライセンス済みコピーがインストールされ、アクティベートされていることを確認します。

### 保護された Microsoft Office ファイルを開けない {#unable-to-open-a-protected-microsoft-office-files}

Microsoft Office の保護ビューが有効の場合、Right Management Extension は保護された Microsoft Excel ファイル（XLS、XLSX）および保護された Microsoft PowerPoint（PPT）ファイルをリモート場所から開くことができません。

### 画像や背景色を含む Microsoft Excel 文書のセルが、透かしの上に表示される {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Excel ドキュメント内のセルに画像や背景色が設定されていて、動的な透かしが適用されている場合、その画像や色がその透かしを覆います。 このアプローチは、透かしがセル内の画像または背景色でカバーされることを意味します。

### 複数の証明書に関するユーザビリティの問題 {#usability-issue-with-multiple-certificates}

クライアント・マシン上に複数の証明書が存在し、ユーザーが証明書選択ダイアログ・ボックスをキャンセルすると、ダイアログ・ボックスが再び表示されます。 ユーザーは、ダイアログボックスを 2 回キャンセルする必要があります。

### 保護されたドキュメントを Microsoft PowerPoint で編集できる {#microsoft-powerpoint-allows-editing-protected-documents}

保護された文書を Microsoft PowerPoint 上で編集しようとすると、「この文書を変更することはできません。変更を保存することはできません。」 しかし、メッセージを閉じた後も、引き続きテキストの追加や編集をおこなうことができます。ただし保護された文書に対する変更は保存されません。

上記の動作は、PowerPoint 2013、PowerPoint 2016、および PowerPoint 2019 で発生します。
