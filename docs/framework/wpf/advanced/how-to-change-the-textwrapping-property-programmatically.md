---
title: Практическое руководство. Изменение свойства TextWrapping программными средствами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 70dc73fe16ebb98e466c4363e5ac26562329dcd4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362270"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>Практическое руководство. Изменение свойства TextWrapping программными средствами
## <a name="example"></a>Пример  
 В следующем примере кода показано, как изменить значение <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> свойства программным способом.  
  
 Три <xref:System.Windows.Controls.Button> элементы помещаются в <xref:System.Windows.Controls.StackPanel> элемент [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Каждый <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие для <xref:System.Windows.Controls.Button> соответствующий обработчик событий в коде. Обработчики событий используют то же имя, что <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> значения, они будут применены к `txt2` при нажатии кнопки. Кроме того, текст в `txt1` ( <xref:System.Windows.Controls.TextBlock> не отображаются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) обновляется в соответствии с изменениями в свойстве.  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
