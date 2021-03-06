---
title: Практическое руководство. Создание простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 157060e784e4169ac8e31c6028ed65f0a9568e0f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373586"
---
# <a name="how-to-create-a-simple-binding"></a>Практическое руководство. Создание простой привязки
В этом примере показано, как создать простое <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`. `Person` Объект определен в пространстве имен `SDKSample`.  
  
 Выделенная строка, содержащий `<src>` элемента в следующем примере создается экземпляр `Person` со `PersonName` значение свойства `Joe`. Это можно сделать в `Resources` раздела и назначенный `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Выделенная строка, содержащий `<TextBlock>` затем привязывает элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство. В результате <xref:System.Windows.Controls.TextBlock> отображается со значением «Joe».  
  
## <a name="see-also"></a>См. также
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
