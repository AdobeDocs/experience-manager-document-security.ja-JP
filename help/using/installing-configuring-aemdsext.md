---
title: AEM Document Security Extension for Microsoft Office のインストールと設定
description: このドキュメントでは、Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office のインストールおよび設定手順を詳しく説明します。
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: 7eb2b2e5ba296b87159978037ae50c702f7d0656
workflow-type: tm+mt
source-wordcount: '2845'
ht-degree: 94%

---

# AEM Document Security Extension for Microsoft Office のインストールと設定{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

このドキュメントでは、Adobe Experience Manager Document Security Extension for Microsoft Office のインストールおよび設定手順を詳しく説明します。

このドキュメントには、次のタスクに関する情報が含まれています。

* Document Security Extension for Microsoft Office のインストール
* LiveCycle Rights Management ES2 以降、または AEM 6.0 Forms 以降の Document Security アドオンを指すインストーラーの事前設定
* デフォルトポリシーの自動適用の設定

## インストールの前に {#before-you-install}

Document Security Extension for Microsoft Office をインストールする前に、以下の事項を確認または実行します。

* [リリースノート](document-security-extension-release-notes.md)を読んでいる。
* Microsoft Office のライセンス認証を完了している。ライセンス認証画面は、Microsoft Office アプリケーションを開いても表示されません。
* Microsoft Windows および Microsoft Office 用の最新のサービスパックがインストールされている。
* サポートされていない言語に対して Document Security for Microsoft Office をインストールする場合は、その前に Office アプリケーションを少なくとも 1 回は開く。

>[!NOTE]
>
>名前に全角文字を含むフォルダーには本ソフトウェアをインストールしないでください。このようなフォルダーにインストールすると、AEM Document Security のメニューが Microsoft Office に表示されません。

>[!NOTE]
>
>64 ビット版のオペレーティングシステムに 32 ビット版の Document Security 拡張機能をインストールすることはできますが、この逆はサポートされていません。つまり、64 ビット版の Document Security Extension for Microsoft Office を 32 ビット版のオペレーティングシステムにインストールすることはできません。

### McAfee VirusScan の無効化 {#disable-mcafee-virusscan}

McAfee VirusScan コンソールで「Buffer Overflow Protection」オプションを無効にします。これにより、Document Security 拡張機能がインストールされたマシンで Office アプリケーションをスムーズに起動できます。また、McAfee VirusScan with On-Access Scan が有効になります。これらの調整は、起動プロセスを妨げる可能性のある競合の防止に役立ちます。

### サードパーティ製プラグインをアンインストールする {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office は、Microsoft Office アプリケーション用のサードパーティ製プラグインをサポートしていません。 この拡張機能はサードパーティ製プラグインと競合するため、Document Security for Microsoft Office をインストールする前に、アドビ製以外の Microsoft Office 向けプラグインをすべてアンインストールする必要があります。サードパーティ製プラグインがインストールされている場合、アドビでは、Document Security for Microsoft Office アプリケーションのサポートを提供できません。

## 必要システム構成 {#system-requirements}

### Document Security Extension クライアント {#document-security-extension-client}

Document Security Extension のインストールに最低限必要なシステム構成は次のとおりです。

* 32 ビット版または 64 ビット版の Microsoft Windows 11 上の Microsoft Office 2019 Professional Plus 英語版、フランス語版、ドイツ語版、日本語版、イタリア語版、スペイン語版、ポルトガル語（ブラジル）版、韓国語版、中国語（簡体字）版または中国語（繁体字）版。

* 32 ビット版または 64 ビット版のMicrosoft Windows 10 （英語、フランス語、ドイツ語、日本語、イタリア語、スペイン語、ブラジル語、ポルトガル語、韓国語、簡体字中国語、繁体字中国語）。

  **メモ：** *Document Security Extension for Microsoft Office は Microsoft Surface シリーズのデバイスでも動作すると想定されます。*

* 32 ビット版または 64 ビット版の Office 2016、2019、および Office 365 の一部としてインストールされた Microsoft Office デスクトップアプリケーションの英語版、フランス語版、ドイツ語版、日本語版、イタリア語版、スペイン語版、ポルトガル語（ブラジル）版、韓国語版、中国語（簡体字）版または中国語（繁体字）版。

  **メモ**：*AEM Document Security Extension for Microsoft Office は Microsoft Office アプリケーション向けのサードパーティ製プラグインをサポートしていません。この拡張機能はサードパーティプラグインと競合する場合があるため、Document Security Extension for Microsoft Office をインストールする前に、アドビ製以外の Microsoft Office アプリケーション用プラグインをアンインストールする必要があります。サードパーティ製プラグインがインストールされている場合、アドビでは、Document Security Extensions for Microsoft Office アプリケーションのサポートを提供できません。*

* 1.3 GHz 以上のプロセッサー
* 2 GB の RAM
* 100 MB のハードディスク容量

### Document Security {#document-security}

Document Security Extension を使用するには、Adobe LiveCycle Rights Management ES2 以降または AEM 6.0 Forms 以降向けの Document Security アドオンに接続できる必要があります。

## Document Security Extension for Microsoft Office のインストール {#installing-document-security-extension-for-microsoft-office}

[ダウンロードページ](download-installer.md)でインストーラーをダウンロードすることができます。インストーラーの実行可能ファイルを直接カスタマイズすることはできませんが、ソフトウェアを対話形式でインストールすることも、サイレントインストールを実行することもできます。ソフトウェアをインストールするには、管理者として Windows にログインします。

32 ビット版と 64 ビット版の Microsoft Office Excel には、それぞれ別のインストーラーが用意されています。32 ビット版 Microsoft Office の場合は、DocumentSecurityExtensionforMicrosoftOffice.exe をダウンロードします。64 ビット版 Microsoft Office の場合は、DocumentSecurityExtensionforMicrosoftOffice64.exe をダウンロードします。

>[!NOTE]
>
>このドキュメントでは、32 ビット版のインストーラーファイル（DocumentSecurityExtensionforMicrosoftOffice.exe）を使用して、各種のコマンドやオプションについて説明します。64 ビット版 Microsoft Office を使用している場合、このドキュメントに記載されている操作を実行するには、64 ビット版のインストーラーファイル（DocumentSecurityExtensionforMicrosoftOffice64.exe）を使用します。

### 無人モードでのインストール {#install-in-silent-mode}

インストーラーファイルから `DocumentSecurityExtensionforMicrosoftOffice.exe` を解凍するには、WinZip などのファイル解凍ユーティリティを使用します。コマンドプロンプトを開き、セットアップファイルが含まれているディレクトリに移動し、次のように入力します。

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

インストーラーは、MSI ファイルとして入手することもでき、これはカスタマイズに使用できます。

### サイレントモードでの MSI ファイルのインストール {#install-an-msi-file-in-silent-mode}

1. ZIP ファイルから `DocumentSecurityExtensionforMicrosoftOffice.msi` ファイルを解凍するには、WinZip などのファイル解凍ユーティリティを使用します。

1. コマンドプロンプトを開き、MSI ファイルが含まれているフォルダーに移動し、次のように入力します。

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Document Security に接続するためのインストーラーの事前設定 {#preconfiguring-the-installer-to-connect-to-document-security}

Microsoft Office インストーラーが LiveCycle または AEM サーバーを指すように、Microsoft Office 用 Document Security 拡張機能を事前設定できます。これにより、Document Security Extension for Microsoft Office をインストールするユーザーは、接続を設定しなくても機能を使用できます。これにより、ユーザーは設定をしなくても、保護されたドキュメントを開くことができます。ただし、新しいドキュメントについては、特定のサーバーを使用するようにクライアントを設定するまで保護できません。

MSI ファイルを作成し設定する方法を以下の手順で説明します。この MSI ファイルにはレジストリ値が含まれています。これらの値は、大規模法人にインストールされている LiveCycle または AEM サーバーを指すように Microsoft Office 用 Document Security 拡張機能のインストーラーを事前設定するのに必要です。

### インストーラーをカスタマイズするための前提条件 {#prerequisites-for-customizing-the-installer}

インストーラーをカスタマイズするには、Orca データベースエディターを使用します。次の手順では、Orca データベースエディターで MSI インストールファイルのコピーを変更してカスタム MSI ファイルを作成する方法を説明します。Orca は、Windows SDK for Windows Server 2008 および .NET Framework 3.5 の一部として使用できます。

<!--

For more information about how to edit Microsoft Windows&reg; Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>カスタム MSI ファイルを作成する前に、すべてのインストーラーファイルの完全なバックアップを作成しておくことをお勧めします。

#### Orca のインストール {#install-orca}

1. Windows SDK for Windows Server 2008 および .NET Framework 3.5 をダウンロードします。
1. \Microsoft SDK\bin フォルダー内の Orca.msi ファイルをダブルクリックします。

   また、インストーラーファイルの MSI バリアントも必要です。アドビサポートに問い合わせて、MSI インストーラーの最新バージョンを入手してください。

   >[!NOTE]
   >
   >インストーラーを実行する前に、DocumentSecurityExtensionforMicrosoftOffice.msi ファイルを必ず閉じてください。Orca で MSI ファイルが使用されている場合は、インストーラーを実行できません。

### MSI ファイルの作成と設定 {#create-and-configure-the-msi-file}

1. **[!UICONTROL スタート／プログラム／Orca]** をクリックします。

1. **[!UICONTROL ファイル／開く]**&#x200B;をクリックし、`DocumentSecurityExtensionforMicrosoftOffice.msi` ファイルを参照します。

1. テーブルのリスト（左側）から「プロパティ」を選択します。

1. Rights Management または Document Security のエンタープライズ版インストールに適用される、以下のキー名の値を編集します。

<table>
 <tbody>
  <tr>
   <td><p><strong>キ</strong><strong>ー</strong><strong>名</strong></p> </td>
   <td><p><strong>説明</strong></p> </td>
   <td><p><strong>キ</strong><strong>ー</strong><strong>値のデフォルト</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>自分の名前を表示します。</p> </td>
   <td><p>デフォルトサーバー</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>ホストサーバーの URL。</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. テーブルのリスト（左側）から「レジストリ」を選択します。

1. 次のキー名の値を編集します。

   | **キー名** | **説明** | **キー値のデフォルト** |
   |---|---|---|
   | `IsDefault` | デフォルトの APS サーバー。 | デフォルトサーバー |

1. 変更したファイルを、元の MSI インストーラーが格納されているのと同じディレクトリに保存します。

   >[!NOTE]
   >
   >一般的には、元の MSI ファイルと同じファイル名（例：`DocumentSecurityExtensionforMicrosoftOffice.msi`）を使用します。

## デフォルトポリシーの自動適用の設定 {#configuring-automatic-application-of-a-default-policy}

設定の一環として、保存されたすべてのドキュメントが Document Security Extension for Microsoft Office で保護されるように、デフォルトポリシーの自動適用を設定できます。

次のいずれかのオプションを指定できます。

* すべてのドキュメントをデフォルトポリシーで保護する。
* サーバーに接続できない場合は、保護されない形式でユーザーがファイルを保存できるようにする。このような柔軟性があれば、ネットワークとの接続が切断されている間（例えば、飛行機に搭乗している間など）にユーザーがドキュメントを作成している場合にも対応できます。

自動適用ポリシー機能を有効にすると、次の場合にドキュメントがデフォルトポリシーで保護されます。

* 新しく作成したドキュメントをユーザーが編集して保存する場合
* 保護されていないドキュメントをユーザーが編集して保存する場合
* ドキュメントをデフォルトの状態で開くアプリケーションをユーザーが起動し、ドキュメントを編集して保存する場合

### MSI ファイルでの自動適用ポリシー機能の設定 {#configure-the-auto-apply-policy-feature-in-the-msi-file}

操作を開始する前に、この記事で前述したように、LiveCycle サーバーまたは AEM Forms サーバーを指すようにインストーラーを事前設定します。

1. **[!UICONTROL スタート／プログラム／Orca]** をクリックします。

1. **[!UICONTROL ファイル／開く]**&#x200B;をクリックし、`DocumentSecurityExtensionforMicrosoftOffice.msi` ファイルを参照します。

1. テーブルのリスト（左側）から「プロパティ」を選択します。

1. 企業向けにインストールされた Rights Management または Document Security に合わせて、以下のキー名の値を編集します。

<table>
 <tbody>
  <tr>
   <td><p><strong>キー名</strong></p> </td>
   <td><p><strong>説明</strong></p> </td>
   <td><p><strong>キ</strong><strong>ー</strong><strong>値のデフォルト</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>自動適用ポリシー機能を有効または無効にします。</p> <p><code>1</code>：有効</p> <p>0：無効</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>ポリシーは、新しいドキュメントを保存するときに使用する GUID です。この値は、自動適用ポリシー機能に適用されます。</p> </td>
   <td><p>RM サーバーに表示される 16 進数のポリシー ID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>サーバーの URL。</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>サーバーのポート番号。</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>初回保存時にドキュメントを保護する目的でクライアントがサーバーに接続できない場合に、Document Security による保護なしでドキュメントを作成できるかどうかを指定します。</p> <p>1：保護されていない保存を許可する </p> <p>0：クライアントがドキュメントを保存するためにサーバーに接続できない場合は新しいドキュメントの作成を許可しない</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` オプションは、ユーザーにすべてのドキュメントを保護するように強制する代わりに、そうするように喚起する場合に便利です。また、このオプションは、ユーザーがネットワークから切断されているときにユーザーがドキュメントを作成したということを知ることができるので便利です。ユーザーによるドキュメントの作成や保存は妨げないようにします。

1. 変更したファイルを、元の MSI ファイルが格納されているのと同じディレクトリに保存します。

   >[!NOTE]
   >
   >一般的には、元の MSI ファイルと同じファイル名（例：`DocumentSecurityExtensionforMicrosoftOffice.msi`）を使用します。

## 新しいドキュメントの自動保護を有効にする {#enabling-automatic-protection-of-new-documents}

管理者は、ユーザーが保存するドキュメントを自動的に保護する機能を有効にできます。管理者は、Document Security Extension for Microsoft Office のインストールプログラムで「自動適用ポリシー」機能を設定します。

自動適用ポリシーが有効になっている場合、ユーザーが保存したすべてのドキュメントはデフォルトのポリシーで保護されます。 この操作は次のような状況で実行します。

* 新規ドキュメントをユーザーが作成し編集して保存するとき
* 保護されていないドキュメントをユーザーが開き編集して保存するとき

自動適用ポリシーの設定については、[ デフォルトポリシーの自動適用の設定 ](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p) を参照してください。

## リボンを使用しないユーザーインターフェイスの有効化 {#enable-ribbon-less-user-interface}

リボンを使用しないユーザーインターフェイスは、Windows レジストリの設定を変更することで有効／無効にすることができます。レジストリを更新し、リボンを使用しないユーザーインターフェイスを有効にするには、次の手順を実行します。

1. 変更する前に、Windows レジストリのバックアップを作成します。詳しい手順については、[Windows レジストリを変更する方法](https://learn.microsoft.com/ja-jp/troubleshoot/windows-server/performance/windows-registry-advanced-users)を参照してください。
1. レジストリエディタで、HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 または HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 を開きます。
1. **「HidePluginUI」**&#x200B;という名前で、新しい Dword（32 ビット）値を作成します。

1. リボンを使用しないユーザーインターフェイスを有効にするには、**HidePluginUI** のプロパティ値を 1 に設定します。

1. レジストリエディターを終了します。

## Microsoft Excel からの印刷時に透かしを付ける方法 {#enable-watermark-for-printing-in-microsoft-excel}

Windows レジストリ設定を変更して、既存のヘッダーとフッターに動的透かしを共存させることができます。レジストリ設定では、印刷中にのみ透かしが有効になります。次の手順を実行して、レジストリを更新し、印刷中に透かしを有効にします。

1. 変更する前に、Windows レジストリのバックアップを作成します。詳しい手順については、[Windows レジストリを変更する方法](https://learn.microsoft.com/ja-jp/troubleshoot/windows-server/performance/windows-registry-advanced-users)を参照してください。
1. レジストリエディタで、HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 または HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 を開きます。
1. 新しいレジストリキー **WatermarkMode** を作成します。
1. WatermarkMode レジストリキーで、DWORD **WatermarkMode** を作成し、DWORD **WatermarkMode** の値を「**1**」に設定します。

1. レジストリエディターを終了します。

>[!NOTE]
>
>Windows エクスプローラーでは、ファイルメニューまたはコンテキストメニューから Microsoft Excel 文書を作成できます。静的メソッドで作成された文書の場合、印刷日を検索または変更することはできません。これは Microsoft Excel による制限です。AEM Document Security の透かしは、文書の印刷日付に依存します。したがって、静的メソッドで作成された文書の透かしは前の日付に戻ります。さらに、ヘッダーとフッターも保持されません。

## ドキュメントにカスタム表紙を追加する方法 {#coverpage}

AEM Document Security for Microsoft Office プラグインがインストールされていないマシン上でも、保護されたドキュメントをユーザーが開こうとする可能性があります。このような PC では、ドキュメントを開くことができませんが、AEM Document Security for Microsoft Office プラグインのダウンロード方法などの情報を含む表紙を表示させることができます。

### 表紙を構成する前に、以下の事項を実行または確認します。 {#before-you-configure-a-cover-page}

* CommonResources.dll ファイルのバックアップを作成する。デフォルトのパス：

   * **（32 ビット版の Office または 32 ビット版の PC の場合）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（32 ビット版の Office または 64 ビット版の PC の場合）** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（64 ビット版の Office または 64 ビット版の PC の場合）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Microsoft Visual Studio 2008 以降がインストールされている。他のユーティリティを使用して DLL ファイルを編集することもできます。
* templates.zip アーカイブを解凍する。アーカイブには、表紙の.xlsx、.docx、および .pptx テンプレートが含まれています。.xlsx、.docx、および .pptx のファイル形式には、指定されたテンプレートのみを使用してください。他のファイルタイプ用に独自のテンプレートを作成することもできます。テンプレートをカスタマイズすることで、独自のメッセージや指示を含めることができます。template.zip は以下にあります。

[ファイルを入手](assets/templates.zip)

### CommonResources.dll ファイルの構成 {#structure-of-the-commonresources-dll-file}

CommonResources.dll ファイルには、リソーステンプレートに関する情報が含まれています。TEMPLATE_FILE と RT_MANIFEST の 2 つの名前識別子が含まれています。カスタム表紙を使用可能にするには、TEMPLATE_FILE の名前識別子を変更します。TEMPLATE_FILE の名前識別子には 6 個のリソースがあります。

<table>
 <tbody>
  <tr>
   <td><p><strong>Resource</strong></p> </td>
   <td><p><strong>対応ファイル </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### テンプレートをカバーページとして設定する方法 {#configure-the-template-as-a-cover-page}

1. Microsoft Visual Studio を開きます。CommonResources.dll ファイルを参照して開き、編集します。

   >[!NOTE]
   >
   >「Solution Explorer」ウィンドウにファイルが表示されない場合は、「ファイルを開く」オプションからファイルを再度開きます。リソースエディターをエディターとして選択します。

1. 「Solution Explorer」のウィンドウで TEMPLATE_FILE ディレクトリを展開し、リソース「101」を削除します。

1. リソースを追加：

   1. Solution Explorer でプロジェクトを選択し、「プロジェクト」メニューから「プロパティ」をクリックします。
   1. 「リソース」タブを選択します。
   1. 「リソースデザイナー」のツールバーで「リソースの追加」にマウスオーバーし、矢印をクリックします。リソースのタイプに「TEMPLATE_FILE」を選択し、「インポート」をクリックします。
   1. **`Add existing file to resources`** ダイアログボックスで、Resource.xlsx ファイルを参照し、「開く」をクリックします。ファイルが「TEMPLATE_FILE」ディレクトリに追加されます。

   >[!NOTE]
   >
   >言語設定が正しいことを確認してください。ニュートラル言語のリソースを削除します。

1. すべてのリソースタイプに対して手順 2 と 3 を繰り返します。

   >[!NOTE]
   >
   >リソースタイプを削除および追加する場合は、順番を維持してください。例えば、101 の後には 102 を設定する必要があります。

### AEM Document Security extension for Microsoft Office のインストーラーにカスタム CommonResources.dll ファイルをパッケージ化する方法  {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

CommonResources.dll ファイルをカスタマイズして、カスタムの表紙を追加できます。ファイルをカスタマイズした後は、すべてのワークステーション上で元のファイルを手動でカスタムファイルに置き換えるか、あるいは自動化された方法でファイルを置き換えることができます。

大規模な環境では、デフォルト `CommonResources.dll file` をカスタム `CommonResources.dll` ファイルに手動で置き換えることは困難で大変な作業です。自己解凍パッケージツール（WinZip Self-Extractor など）を使用することで、カスタムの CommonResources.dll ファイルを AEM Document Security Extension for Microsoft Office インストーラーにパッケージ化することができます。パッケージ化した後は、カスタムインストーラーをすべてのワークステーションに配布することができます。この方法により、デフォルトの `CommonResources.dll` ファイルをカスタムファイルで置き換えるのに必要な時間を短縮できます。また、必要な CommonResources.dll ファイルをすべてのワークステーションに確実に提供する上でも役立ちます。自己解凍のパッケージングツールは、ファイルを自動的に置き換える様々な方法の 1 つにすぎません。お使いの環境に適した任意の方法を選択できます。

AEM Document Security extension for Microsoft Office のインストーラーにカスタムの `CommonResources.dll`ファイルをパッケージ化するには、次の手順を実行します。

1. 自己解凍型のパッケージツール（例：WinZip Self-Extractor など）をインストールします。
1. 新しいフォルダーを作成します。例えば、「YOUR_FOLDER_NAME」と名前を付けます。
1. 新しく作成されたフォルダーに、AEM Document Security Extension とカスタムの CommonResources.dll ファイルの元のインストーラーを配置します。
1. フォルダー内にバッチファイルを作成します。例えば、「YOUR_FOLDER_NAME\Installer.bat」と名前を付けます。
1. 編集用のバッチファイルを開き、次のコードをバッチファイルに追加します。

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   JEE 上で LiveCycle Rights Management ES4 およびバージョン 11.0.0 以外の LiveCycle または AEM Forms を使用している場合は、レジストリキーのパスを次のように置き換えます。

   * （LiveCycle® Rights Management ES2 およびバージョン 9.0 の場合）：*HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * （LiveCycle® Rights Management ES3 およびバージョン 10.0 の場合）
   * （LiveCycle® Rights Management ES4 およびバージョン 11.0 の場合）HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * （AEM 6.0 Forms on JEE 以降の場合）HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 上記のコードでは、YOUR_FOLDER_NAME のインスタンスをすべて、手順 2 で作成したフォルダー名に置き換えます。
1. **（.exe の拡張子を持つ、AEM Document Security Extension for Microsoft Office のインストーラーのみ）** 次のコード行を置き換えます。

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`を次のタグに置換します。

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. バッチファイルを保存して閉じます。
1. 自己解凍型のパッケージ作成ツールを使用して、次を含むフォルダーにまとめ、パッケージ化します。

   * カスタムの CommonResources.dll ファイル
   * AEM Document Security Extension for Microsoft Office の元のインストーラー
   * およびバッチファイル

   >[!NOTE]
   >
   >自己解凍パッケージが管理者として実行されるように設定されていて、
   >解凍の完了時にバッチファイルを自動的に実行することを確認します。

これで、カスタムの CommonResources.dll ファイルを含む AEM Document Security Extension for Microsoft Office パッケージの自己解凍インストーラーが完成し、配布準備が整いました。
