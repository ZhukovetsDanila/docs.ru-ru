---
title: Практическое руководство. Печать формы Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 80bf88ad048e55a381d034d2a796de6f77f8691c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714155"
---
# <a name="how-to-print-a-windows-form"></a>Практическое руководство. Печать формы Windows Forms
Как часть процесса разработки обычно требуется распечатать копию в форму Windows. В следующем примере кода показано, как распечатать копию текущей формы с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Это полный пример кода, содержащий `Main` метод.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   У вас нет разрешения на доступ к принтеру.  
  
-   Нет нет установленных принтеров.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы запустить этот пример кода, необходимо разрешение на доступ к принтеру, используемые с компьютера.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Printing.PrintDocument>
- [Практическое руководство. Вывод изображений с использованием GDI +](how-to-render-images-with-gdi.md)
- [Практическое руководство. Печать графических изображений в Windows Forms](how-to-print-graphics-in-windows-forms.md)
