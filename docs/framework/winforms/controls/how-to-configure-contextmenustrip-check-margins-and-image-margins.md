---
title: Практическое руководство. Руководство Настройка полей флажков и значков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], configuring check and image margins
- ContextMenuStrips [Windows Forms], configuring check and image margins
- margins [Windows Forms], setting check and image in Windows Forms ContextMenuStrips
ms.assetid: 3391c4c2-0c9e-4aa4-9492-13ff7644bdf2
ms.openlocfilehash: 8527c8f2195c586ba7d9c61c5c2ea1fa26bf53f8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715222"
---
# <a name="how-to-configure-contextmenustrip-check-margins-and-image-margins"></a>Практическое руководство. Руководство Настройка полей флажков и значков
Элемент управления <xref:System.Windows.Forms.ContextMenuStrip> можно настраивать, устанавливая свойства <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> и <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> в различных сочетаниях.   
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как установить и настроить поля флажков и значков для элемента управления <xref:System.Windows.Forms.ContextMenuStrip>.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [Элемент управления ToolStrip](toolstrip-control-windows-forms.md)
- [Практическое руководство. Включение полей флажков и значков для элементов управления ContextMenuStrip](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
