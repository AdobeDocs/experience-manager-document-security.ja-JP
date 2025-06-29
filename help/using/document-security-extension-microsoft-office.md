---
title: AEM Document Security Extension for Microsoft® Officeの紹介
description: Document Security Extension for Microsoft® Office を使用することで、Microsoft® Office ファイルに事前定義済みの機密設定を適用できます。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: ht
source-wordcount: '1248'
ht-degree: 100%

---

# Microsoft® Office 用 AEM Document Security 拡張機能の紹介{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office を使用すると、知的財産を含む Word、Excel、および PowerPoint ファイルを、許可したユーザーのみが使用できるようにすることができます。Microsoft® Office 用 Document Security 拡張機能を使用することにより、事前定義済みの機密設定をファイルに適用できます。

Document Security Extension for Microsoft® Office は、Adobe Experience Manager Forms の LiveCycle Rights Management とドキュメントセキュリティを強化します。これにより、Office ファイルが保護され、許可されたユーザーは、設定された機密設定に従って、ポリシーで保護されたファイルにアクセスできるようになります。

## Document Security による知的財産の保護の仕組み {#how-document-security-protects-intellectual-property}

ドキュメントセキュリティにより、許可されたユーザーだけが、知的財産を含んだファイルを使用できるようになります。Document Security を利用すると、機密ポリシーを使用してファイルを保護できます。*ポリシー*&#x200B;は、機密設定と、許可されたユーザーの一覧を含む、情報のコレクションです。ポリシーを適用したファイルを受信者がどのように使用できるかは、ポリシーで指定した設定で決まります。例えば、受信者がテキストの印刷やコピー、変更内容の保存を行えるかどうかを指定できます。

ポリシーを作成するのは Document Security 管理者およびユーザーです。管理者は、許可されたすべてのユーザーが使用できる組織ポリシーを作成します。管理者またはポリシー設定コーディネータは、ユーザーのサブセットで使用できる&#x200B;*ポリシーセット*&#x200B;と呼ばれるポリシーグループを作成することもできます。ユーザーは自分だけが使える独自のポリシーを作成できます。管理者、ポリシー設定コーディネーター、ユーザーは、Document Security web ページを使用してポリシーを作成します。

ポリシーは Document Security に保存されますが、Word、Excel、PowerPoint のいずれかを使用してファイルに適用できます。ファイルにポリシーを適用すると、そのファイルに含まれている情報が、ポリシーで指定された機密設定により保護されます。ポリシーで保護されたファイルを配布すると、許可された受信者のみがそのコンテンツにアクセスできます。

ポリシーを使用してファイルを保護すると、配布後もファイルを継続的に管理できます。イベントを監査すると、受信者がファイルを使用するタイミングと方法を追跡できます。また、ポリシーを変更したり、ユーザーがファイルにアクセスし続けることを禁止したり、ファイルに添付されているポリシーを変更したりすることもできます。

## ポリシーの仕組み {#how-policies-work}

ポリシーは、許可されたユーザーおよび知的財産に適用される機密設定に関する情報で構成されます。Document Security は、リンクされた LDAP または Active Directory リストに含まれるユーザーを認識します。また、Document Security への登録を招待された人や、管理者がアカウントを作成した人もユーザーになれます。

ポリシーで保護されたファイルを受信者がどのように使用できるかは、ポリシーの機密設定で決まります。ポリシーでは、例えば、受信者がファイルを印刷したり、内容を他のファイルにコピーしたり、保護されたファイルに変更内容を保存したりできるかどうかを指定します。また、様々なユーザーに応じて異なる機密設定を指定することもできます。

ファイルにポリシーを適用すると、そのファイルに含まれている情報が、ポリシーで指定された機密設定により保護されます。ファイルを配布すると、それを開こうとする受信者の認証が Document Security によっておこなわれ、ポリシーで指定されている権限に従って受信者にアクセスが許可されます。

ファイルにポリシーを適用した後は、ポリシーの機密設定をいつでも変更できます。 許可されたユーザーを追加または削除したり、ファイルを受け取った後にユーザーの権限を変更したりできます。ファイルに適用されたポリシーは変更できます。また、ファイルへのアクセスを取り消すことで、ファイルのコピーを持っているユーザーがそのファイルを開けないようにすることもできます。

オフラインアクセスがポリシーで許可されている場合、受信者は、ポリシーで保護されたファイルを、ポリシーで指定された期間、オフライン（アクティブなインターネット接続やネットワーク接続がない状態）で使用することもできます。

## ポリシーで保護されたファイルの仕組み {#how-policy-protected-files-work}

ポリシーで保護された Word、Excel および PowerPoint ファイルを開き、使用するには、そのユーザーがポリシーの受信者として含まれている必要があります。または、匿名アクセスを許可する必要があります。また、Microsoft® Office 用 Document Security 拡張機能がインストールされている必要があります。Microsoft® Office 用 Document Security 拡張機能を持っていないユーザーに、ポリシーで保護されたファイルを渡す場合は、ソフトウェアのコピーを渡すことができます。または、web サイトからダウンロードする方法を教えることもできます。インストーラーがない場合は、[ダウンロードページ](https://experienceleague.adobe.com/ja/docs/experience-manager-document-security/using/download-installer)からダウンロードできます。

ポリシーで保護されたファイルをユーザーが開こうとすると、Microsoft® Office 用 Document Security 拡張機能が Document Security に接続して、ユーザーの認証を行います。ファイルの使用状況を監査するように Document Security が設定されている場合は、ファイルの使用状況が監査中であることを示す通知が表示されます。ユーザーに付与されるファイル権限は Document Security によって決定され、ユーザーは、次の条件の下でポリシー設定に従ってファイルを使用できます。

* ポリシーで指定された有効期間内。
* 管理者またはポリシーの適用者がファイルへのアクセスを無効にするか、ポリシーを変更するまで。

  ポリシーの適用者がポリシーを変更するかファイルへのアクセスを無効にした場合、ユーザーが既にファイルを持っていても、そのファイルに対するユーザーの権限が変更または削除されます。ファイル自体が無効になっている場合は、最新のコピーを取得するための URL をユーザーに提供できます。

  ポリシーでオフラインアクセスが許可されている場合、ユーザーは、指定されたオフラインリース期間中、インターネットまたはネットワーク接続がなくても、ポリシーで保護されたファイルを開くことができます。オフラインリース期間が終了したら、ユーザーはオンラインにして、Document Security と同期する必要があります。その結果、新しいリース期間が始まります。

  ポリシーでオフラインアクセスが許可されている場合、ユーザーは、指定されたオフラインリース期間中、インターネットまたはネットワーク接続がなくても、ポリシーで保護されたファイルを開くことができます。新しいファイルを開こうとするイベントも、元のファイルの場合と同じように、監査され記録されます。

## Document Security を使用したファイルの保護 {#using-document-security-to-protect-your-files}

ポリシーを使用すると、様々な状況でファイルを保護できます。

例えば、あるメーカーが新しい製品の部品を提供するベンダーから入札を受けているとします。メーカーは、入札者に提案書の最終決定に必要な専有情報を提供する必要があります。メーカーは、Document Security を使用して、入札者がファイルを開いて情報を閲覧できるように指定したポリシーでファイルを保護します。ただし、入札者はファイルの変更、印刷、コピーをおこなうことはできず、権限を持たないユーザーはファイルを開くことができません。

入札を承認すると、メーカーはポリシーを更新して、入札者に印刷、コピー、変更をローカルに保存する権限を付与します。また、メーカーは成功しなかった入札者も削除し、ファイルを開く権限を取り消します。

成功した入札者と協力しながら、メーカーのエンジニアはファイルの設計仕様の一部を変更します。新しい仕様を公開するために、メーカーは一部のファイルへのアクセスを無効にして、新しいバージョンを公開します。入札に成功したベンダーのエンジニアがこのファイルを開こうとすると、ファイルへのアクセスが無効になったというメッセージが表示されます。このメッセージには URL が含まれており、エンジニアはそこからファイルの新しいバージョンをダウンロードできます。

## 追加情報 {#additional-information}

次の表に、AEM Document Security の参考情報を記載します。

<table >
 <tbody>
  <tr>
   <th><p>情報</p> </th>
   <th><p>参照先</p> </th>
  </tr>
  <tr>
   <td><p>AEM Forms 管理者ヘルプ</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">管理ヘルプ</a>または Document Security 管理ページで、ページの右上にある「ヘルプ」リンクをクリックしてください。</p> </td>
  </tr>
  <tr>
   <td><p>現在のバージョンに関するパッチアップデート、テクニカルノート、および追加情報</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/ja?support-solution=General&amp;support-tab=home&amp;lang=ja#support">Experience Cloud のテクニカルサポート</a></p> </td>
  </tr>
 </tbody>
</table>
