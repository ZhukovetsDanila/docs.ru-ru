---
title: Практическое руководство. Декорирование дочерних объектов Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 9f840180edf55c3e10e6859dfc2b9f4b6495b878
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358201"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Практическое руководство. Декорирование дочерних объектов Panel
В этом примере показано, как программным способом привязки декоративного элемента к дочерним элементам указанного <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Пример  
 Для привязки декоративного элемента к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:  
  
1.  Объявите новый <xref:System.Windows.Documents.AdornerLayer> и вызовите `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой графических элементов для элемента, дочерние элементы которого нужно декорировать.  
  
2.  Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента для каждого дочернего элемента.  
  
 Следующий пример связывает SimpleCircleAdorner (как показано выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
## <a name="see-also"></a>См. также
- [Общие сведения о декоративных элементах](adorners-overview.md)
