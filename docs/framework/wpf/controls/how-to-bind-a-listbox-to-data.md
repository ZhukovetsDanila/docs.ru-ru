---
title: Практическое руководство. Привязка элемента ListBox к данным
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 2cbcb0fb859605c33e2d92559b4a47aa1725472c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372885"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Практическое руководство. Привязка элемента ListBox к данным
Разработчик приложения можно создать <xref:System.Windows.Controls.ListBox> элементы управления без указания содержимого каждого <xref:System.Windows.Controls.ListBoxItem> отдельно. Можно использовать привязку данных для привязки данных для отдельных элементов.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.ListBox> , заполняющий <xref:System.Windows.Controls.ListBoxItem> элементов путем привязки данных к источнику данных с именем *цвета*. В этом случае необязательно использовать <xref:System.Windows.Controls.ListBoxItem> теги для указания содержимого каждого элемента.  
  
## <a name="example"></a>Пример  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [Элементы управления](../advanced/optimizing-performance-controls.md)
