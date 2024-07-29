---
title: AEM Document Security Extension for Microsoft Office のトラブルシューティング
description: AEM Document Security Extension for Microsoft Office のインストール、設定、使用に問題がある場合は、この記事に記載されている手順に従ってください。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: ht
source-wordcount: '284'
ht-degree: 100%

---

# AEM Document Security Extension for Microsoft Office のトラブルシューティング{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## インストールと設定に関する問題のトラブルシューティング {#troubleshootinginstallationandconfiguration}

AEM Document Security Extension for Microsoft Office をインストールまたは設定する際に問題が発生した場合は、[インストール](installing-configuring-aemdsext.md)記事のインストールの前にの節に記載されている手順に注意深く従っていることを確認します。

インストールおよび設定をすべてドキュメントどおりに行っている場合は、次の節を参照して、発生している問題に類似の問題があるか確認します。

### Document Security Extension が Microsoft Office アプリケーションの読み込みに失敗する {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows レジストリの LoadBehavior プロパティは、Document Security プラグイン実行時の動作を指定します。LoadBehavior プロパティを 3 に設定すると、すべてのプラグインを自動的に読み込みます。Document Security Extension for Microsoft Office をインストールする前に、LoadBehavior プロパティの値が 3 に設定されていることを確認してください。

1. 変更する前に、Windows レジストリのバックアップを作成します。詳しい手順については、[Windows レジストリを変更する方法](https://learn.microsoft.com/ja-jp/troubleshoot/windows-server/performance/windows-registry-advanced-users)を参照してください。
1. レジストリエディターを開き、HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin または HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM に移動します。
1. **LoadBehavior** プロパティの値を 3 に設定します。

1. レジストリエディターを終了します。

LoadBehavior の詳細については、[VSTO アドインのレジストリエントリ](https://learn.microsoft.com/ja-jp/visualstudio/vsto/registry-entries-for-vsto-add-ins?view=vs-2022&amp;redirectedfrom=MSDN#LoadBehavior)の記事を参照してください。

## 管理タスクのトラブルシューティング {#admintasks}

この節では、インストールされている AEM Document Security Extension で発生し得る問題について説明します。

### Document Security Extension をインストールした後、Microsoft Office アプリケーションがスムーズに起動しなくなった {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Document Security Extension がインストールされ、McAfee VirusScan の On-Access Scan 機能が有効になっている状態で Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console の「Buffer Overflow Protection」を無効にします。
