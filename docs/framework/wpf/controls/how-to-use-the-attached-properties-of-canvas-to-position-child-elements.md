---
title: Практическое руководство. Использование вложенных свойств Canvas для расположения дочерних элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: a34bac644bd0fa4c15d76d72d0502b311c49d018
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365338"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Практическое руководство. Использование вложенных свойств Canvas для расположения дочерних элементов
В этом примере показано использование вложенных свойств <xref:System.Windows.Controls.Canvas> для размещения дочерних элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере добавляется четыре <xref:System.Windows.Controls.Button> элементы как дочерние элементы родительского элемента <xref:System.Windows.Controls.Canvas>. Каждый элемент представлен <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, и <xref:System.Windows.Controls.Canvas.Top%2A>.
Каждый <xref:System.Windows.Controls.Button> располагается относительно родительского элемента <xref:System.Windows.Controls.Canvas> и в соответствии с назначенным значением свойства.  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [Общие сведения о панелях](panels-overview.md)
- [Разделы практического руководства](canvas-how-to-topics.md)
- [Общие сведения о присоединенных свойствах](../advanced/attached-properties-overview.md)
