---
title: Xamarin.Forms の XAML のコンパイル
description: この記事では、どの XAML コンパイルできます Xamarin.Forms XAML コンパイラ (XAMLC) で中間言語 (IL) に直接について説明します。
ms.prod: xamarin
ms.assetid: 9A2D10A6-5DFC-485F-A75A-2F7B98314025
ms.technology: xamarin-forms
author: charlespetzold
ms.author: chape
ms.date: 08/22/2018
ms.openlocfilehash: de1ac47a56bf8d75eefb2ed6c7237f2f63f56ecc
ms.sourcegitcommit: e268fd44422d0bbc7c944a678e2cc633a0493122
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50105949"
---
# <a name="xaml-compilation-in-xamarinforms"></a>Xamarin.Forms の XAML のコンパイル

_XAML は、必要に応じて、XAML コンパイラ (XAMLC) で中間言語 (IL) に直接コンパイルできます。_

XAML のコンパイルには、さまざまな利点を提供しています。

- XAML のコンパイル時チェックを実行し、エラーがあればユーザーに知らせます。
- XAML 要素の読み込みとインスタンス化の時間を短縮します。
- .xaml ファイルを含めないことで、最終アセンブリのファイル サイズを減らします。

既定では下位互換性を確保する XAML のコンパイルは無効です。 追加することで、アセンブリとクラス レベルで有効にする、 [ `XamlCompilation` ](xref:Xamarin.Forms.Xaml.XamlCompilationAttribute)属性。

次のコード例では、アセンブリ レベルで有効にすると XAML のコンパイルを示しています。

```csharp
using Xamarin.Forms.Xaml;
...
[assembly: XamlCompilation (XamlCompilationOptions.Compile)]
namespace PhotoApp
{
  ...
}
```

この例では、コンパイル時に、アセンブリ内に含まれるすべての XAML のチェックが実行され、実行時ではなく、コンパイル時に報告されている XAML エラー。 そのため、`assembly`プレフィックス、 [ `XamlCompilation` ](xref:Xamarin.Forms.Xaml.XamlCompilationAttribute)属性は、属性がアセンブリ全体に適用されることを指定します。

> [!NOTE]
> [ `XamlCompilation` ](xref:Xamarin.Forms.Xaml.XamlCompilationAttribute)属性と[ `XamlCompilationOptions` ](xref:Xamarin.Forms.Xaml.XamlCompilationOptions)に列挙型が存在する、`Xamarin.Forms.Xaml`名前空間は、それらを使用するインポートする必要があります。

次のコード例では、クラス レベルで有効にすると XAML のコンパイルを示しています。

```csharp
using Xamarin.Forms.Xaml;
...
[XamlCompilation (XamlCompilationOptions.Compile)]
public class HomePage : ContentPage
{
  ...
}
```

この例では、コンパイル時に XAML のチェックでは、`HomePage`クラスが実行され、エラーは、コンパイル プロセスの一部として報告します。

> [!NOTE]
> Xamarin.Forms アプリケーションのデータ バインディングのパフォーマンスを向上させるためには、コンパイル済みのバインドを有効にすることができます。 詳細については、次を参照してください。[コンパイル バインド](~/xamarin-forms/app-fundamentals/data-binding/compiled-bindings.md)します。

## <a name="related-links"></a>関連リンク

- [`XamlCompilation`](xref:Xamarin.Forms.Xaml.XamlCompilationAttribute)
- [`XamlCompilationOptions`](xref:Xamarin.Forms.Xaml.XamlCompilationOptions)
