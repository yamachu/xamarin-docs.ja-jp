---
title: Xamarin.Mac – 関連ドキュメント
description: このドキュメントには、Xamarin.Mac 開発者向けのドキュメントのリンクがあります。Xamarin.iOS ドキュメント、Apple の Mac Dev Center、Xamarin.Mac でユーザー インターフェイスをビルドする方法について説明したさまざまなガイドにアクセスできます。
ms.prod: xamarin
ms.assetid: 0a282c58-1c37-4f73-8440-85de2daf454a
ms.technology: xamarin-mac
author: lobrien
ms.author: laobri
ms.date: 12/02/2016
ms.openlocfilehash: ae1ac9b40a0e6a62076a6143e64fa8beb82df6c5
ms.sourcegitcommit: e268fd44422d0bbc7c944a678e2cc633a0493122
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50107317"
---
# <a name="xamarinmac-related-documentation"></a>Xamarin.Mac – 関連ドキュメント

Xamarin.Mac に関する質問の資料は、[developer.xamarin.com](~/mac/get-started/index.md) の Mac セクション以外にも、次の 3 か所にあります。

- [**Xamarin.iOS のドキュメント**](~/ios/get-started/index.md): (主に AppKit/UIKit 以外の) 多くの API には、iOS と macOS バージョンであまり大きな違いはありません。 `UIFoo` という名前の iOS の API がある場合、macOS には `NSFoo` という同様な名前の API があります。 これらの例は、通常に既に C# にあります。

- **Apple の [Mac Dev Center](https://developer.apple.com/devcenter/mac/)**: Objective-C での呼び出しに使用する API の例の多くは、簡単な方法で C# に変換できます。 これを行う方法については、「[Understanding Mac API](~/mac/app-fundamentals/mac-apis.md)」 (Mac の API を理解する) を参照してください。

- [**Stack Overflow**](http://stackoverflow.com/): 「[How do I auto expand all nodes in an NSOutlineView](http://stackoverflow.com/questions/519751/nsoutlineview-auto-expand-all-nodes)」 (NSOutlineView でのすべてのノードの自動展開の方法) などの簡単な質問が充実しています。 これらの例は多くの場合 Objective-C 用で、C# に変換する必要がありますが、C# 用の回答も一部あります。

## <a name="user-interface"></a>ユーザー インターフェイス

Xamarin.Mac アプリケーションで C# と .NET を使用している場合、開発者は、*Objective-C* と *Xcode* を使用する開発者が使用しているのと同じユーザー インターフェイス コントロールを使用できます。 Xamarin.Mac は直接 Xcode と統合できるため、開発者は Xcode の_Interface Builder_を使用して、アプリのユーザー インターフェイスを作成して維持できます (または、必要に応じて C# コードで直接作成することも可能です)。

以下のガイドでは、Xamarin.Mac アプリケーションで macOS 要素を使用する方法を詳細に説明します。

- [Windows](~/mac/user-interface/window.md)
- [ダイアログ](~/mac/user-interface/dialog.md)
- [アラート](~/mac/user-interface/alert.md)
- [メニュー](~/mac/user-interface/menu.md)
- [ツールバー](~/mac/user-interface/toolbar.md)
- [テーブル ビュー](~/mac/user-interface/table-view.md)
- [アウトライン ビュー](~/mac/user-interface/outline-view.md)
- [ソース リスト](~/mac/user-interface/source-list.md)
