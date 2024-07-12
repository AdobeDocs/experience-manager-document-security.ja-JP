---
title: AEM Document Security Extension for Microsoft Office のトラブルシューティング
description: AEM Document Security Extension for Microsoft Office のインストール、設定、使用に問題がある場合は、この記事に記載されている手順に従ってください。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 100%

---

# AEM Document Security Extension for Microsoft Office のトラブルシューティング{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## インストールと設定に関する問題のトラブルシューティング {#troubleshootinginstallationandconfiguration}

AEM Document Security Extension for Microsoft Office をインストールまたは設定する際に問題が発生した場合は、[インストール](installing-configuring-aemdsext.md)記事を開き、「インストールの前に」の節に記載されている手順に注意深く従ってください。

インストールおよび設定をすべてドキュメントどおりにおこなっている場合は、以降の節を参照して、発生している問題に類似の問題があるか確認してください。

### Document Security Extension for Microsoft Office が起動に失敗する {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows レジストリの LoadBehavior プロパティは、Document Security プラグイン実行時の動作を指定します。LoadBehavior プロパティを 3 に設定すると、すべてのプラグインを自動的に読み込みます。Document Security Extension for Microsoft Office をインストールする前に、LoadBehavior プロパティの値が 3 に設定されていることを確認してください。

1. Windows レジストリを変更する前に、バックアップを作成してください。詳しい手順については、[Windows レジストリを変更する方法](https://support.microsoft.com/ja-jp/kb/136393)を参照してください。
1. レジストリエディターを開き、HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin または HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM に移動します。
1. **LoadBehavior** のプロパティ値を 3 に設定します。

1. レジストリエディターを終了します。

LoadBehavior の詳細については、[VSTO アドインのレジストリエントリ](https://msdn.microsoft.com/ja-jp/library/bb386106.aspx#LoadBehavior)の記事を参照してください。

## 管理タスクのトラブルシューティング {#admintasks}

この節では、インストールされている AEM Document Security Extension で発生し得る問題について説明します。

### Document Security Extension をインストールした後、Microsoft Office アプリケーションがスムーズに起動しなくなった {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Document Security Extension がインストールされ、McAfee VirusScan の On-Access Scan 機能が有効なコンピューターで Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console の「Buffer Overflow Protection」オプションを無効にしてください。
