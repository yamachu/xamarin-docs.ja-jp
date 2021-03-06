---
title: Xamarin.iOS のアプリ グループ機能
description: アプリケーションに機能を追加するには、多くの場合、追加のプロビジョニングの設定が必要です。 このガイドでは、アプリ グループの機能に必要な設定について説明します。
ms.prod: xamarin
ms.assetid: 0A61220B-BBAC-492B-9D3B-578986E64064
ms.technology: xamarin-ios
author: lobrien
ms.author: laobri
ms.date: 03/15/2017
ms.openlocfilehash: 4ce04f21a3e520fea9da5d538fb7cc0ac098ad31
ms.sourcegitcommit: e268fd44422d0bbc7c944a678e2cc633a0493122
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50119862"
---
# <a name="app-group-capabilities-in-xamarinios"></a>Xamarin.iOS のアプリ グループ機能

_アプリケーションに機能を追加するには、多くの場合、追加のプロビジョニングの設定が必要です。このガイドでは、アプリ グループの機能に必要な設定について説明します。_

アプリ グループを使用すると、さまざまなアプリケーション (またはアプリケーションとその拡張機能) から共有ファイルの保存場所にアクセスできます。 アプリ グループは次のようなデータに使用できます。

*   [Apple Watch の設定](~/ios/watchos/app-fundamentals/settings.md)
*   [共有 NSUserDefaults](~/ios/app-fundamentals/user-defaults.md)
*   [共有ファイル](~/ios/watchos/app-fundamentals/parent-app.md#files)

## <a name="configure-a-new-app-group"></a>新しいアプリ グループを構成する

共有の場所は、 [アプリ グループ](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/EntitlementKeyReference/Chapters/EnablingAppSandbox.html#//apple_ref/doc/uid/TP40011195-CH4-SW19)を使用して構成します。アプリ グループは、Apple Developer Center [](https://developer.apple.com/account/)の **[Certificates, Identifiers & Profiles]** \(証明書、ID、プロファイル\) セクションで構成します。  また、この値は、各プロジェクトの各 Entitlements.plist で参照する必要があります。

アプリ グループには識別子があります。通常、この識別子は、group. プレフィックスを含むバンドル ID です。 たとえば、バンドル ID `com.xamarin.WatchSettings` のアプリ グループは `group.com.xamarin.WatchSettings`です。

新しいアプリ グループを作成するには、次の手順を実行します。

1.  Apple の [iOS Developer Center](https://developer.apple.com/account/) にアクセスし、 **[アカウント]**  を開きログインします。
2.  **[Certificates, IDs & Profiles]** \(証明書、ID、およびプロファイル\) を選択します。
3.   **[Identifiers]** \(識別子\) の下で  **[App Groups]** \(アプリ グループ\) を選択し、 **+** ボタンをクリックして、新しいグループを作成します。
4.  新しいグループ用に  **[名前]** と  **[Identifier]** \(識別子\) を入力し、 **[続ける]** ボタンをクリックします。 
   
    ![アプリ グループの追加の詳細](app-groups-capabilities-images/image52.png)

5.   **[登録]** ボタンをクリックしてグループを作成し、 **[完了]** をクリックして登録されたアプリ グループの一覧に戻ります。

## <a name="configure-an-app-to-use-app-groups"></a>アプリ グループを使用するアプリを構成する

アプリ グループを作成したら、アプリから使用できるようにアプリ ID を構成します。

次の手順で行います。

1.  Apple の  [iOS Developer Center](https://developer.apple.com/account/) にアクセスし、Apple Developer アカウントでログインします。
2.   **[Program Resources]** \(プログラム リソース\) メニューから **[Certificates, IDs & Profiles]** \(証明書、ID、およびプロファイル\) を選択します。
3.   **[Identifiers]** \(識別子\) の下で  **[App IDs]** \(アプリ ID\) を選択し、 **+** ボタンをクリックして、新しい ID を作成します。
4.  App ID の [Name]\(名前\) を入力し、[Explicit App ID]\(明示的な App ID\) を指定します。
5.   **[App Services]** \(アプリ サービス\) で  **[App Groups]** \(アプリ グループ\) を有効にして [続ける] ボタンをクリックします。

    ![アプリ グループの App Services を追加する](app-groups-capabilities-images/image53.png)

6.  設定を確認し、 **[登録]** ボタンをクリックしてアプリ ID を作成します。
7.   **[完了]** ボタンをクリックして登録したアプリ ID の一覧に戻ります。
8.  新しく作成したアプリ ID を一覧から選択し、 **[編集]** ボタンをクリックします。

    ![一覧からアプリ ID を選択する](app-groups-capabilities-images/image54.png)

9.  [サービス] の  **[App Group]** \(アプリ グループ\) の下の  **[編集]** ボタンをクリックします。

    ![一覧からアプリ ID を選択する](app-groups-capabilities-images/image55.png)

10. 上の手順で作成したアプリ グループを選択し、 **[続ける]** ボタンをクリックします。

    ![アプリ グループを追加する](app-groups-capabilities-images/image56.png)

11.  **[Assign]** \(割り当て\) ボタン、 **[完了]** ボタンの順にクリックし、登録したアプリ ID の一覧に戻ります。
12. アプリ グループを使用するすべてのアプリ (または拡張機能) についてこれらの手順を繰り返します。

## <a name="next-steps"></a>次の手順
 
以下のリストでは、実行する必要がある可能性のある追加の手順について説明します。

* アプリでフレームワークの名前空間を使用します。
* アプリに必要な権利を追加します。 必要な権利とその追加方法については、[権利の使用](~/ios/deploy-test/provisioning/entitlements.md)に関するガイドを参照してください。
* アプリの  **[iOS バンドル署名]** で、 **[カスタムの権利]** が **Entitlements.plist** に確実に設定されているようにします。 これは、デバッグと iOS シミュレーターのビルドに対する既定の設定では _"ありません"_ 。

App Services で問題が発生した場合は、メイン ガイドの[トラブルシューティング](~/ios/deploy-test/provisioning/capabilities/index.md)のセクションを参照してください。