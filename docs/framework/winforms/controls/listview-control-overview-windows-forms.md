---
title: Общие сведения об элементе управления ListView (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: d62c0081c128693861a9fd21360f09f65d485a79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709810"
---
# <a name="listview-control-overview-windows-forms"></a>Общие сведения об элементе управления ListView (Windows Forms)
Элемент управления <xref:System.Windows.Forms.ListView> Windows Forms отображает список элементов со значками. Представление списка можно использовать для создания пользовательского интерфейса, аналогичного правой области окна проводника. Элемент управления имеет четыре режима представления: LargeIcon, SmallIcon, списка и сведений.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Что делать с элементом управления ListView  
  
> [!NOTE]
>  Дополнительный режим просмотра плитки, доступна только в ОС Windows Server 2003 и Windows XP. Дополнительные сведения см. в разделе [Как Включение вида мозаики в Windows Forms элемента управления ListView](how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 В режиме LargeIcon отображаются крупные значки, рядом с текстом элемента; элементы появляются в нескольких столбцах, если элемент управления является достаточно большим. Режим SmallIcon аналогичен за исключением того, что отображается мелких значков. Режим списка отображаются мелкие значки, но всегда находится в одном столбце. Режим сведений отображаются элементы в нескольких столбцах. Подробную информацию см. в разделе [Практическое руководство. Добавление столбцов в Windows Forms элемента управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md). Режим представления определяется <xref:System.Windows.Forms.ListView.View%2A> свойство. Все режимы представлении можно отобразить изображения из списков изображений. Подробную информацию см. в разделе [Практическое руководство. Отображение значков Windows Forms элемента управления ListView](how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 В следующей таблице перечислены некоторые из <xref:System.Windows.Forms.ListView> члены и представления, они допустимы в.  
  
|Член ListView|Просмотр|  
|---------------------|----------|  
|Свойство <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Свойство <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Свойство <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.Tile>|  
|Событие<xref:System.Windows.Forms.ListView.DrawSubItem> |<xref:System.Windows.Forms.View.Details>|  
|Метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>или <xref:System.Windows.Forms.View.Tile>|  
|Метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.Tile>|  
|Свойство <xref:System.Windows.Forms.ListView.Groups%2A>|Все представления, за исключением <xref:System.Windows.Forms.View.List>|  
|Свойство <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Свойство <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>или <xref:System.Windows.Forms.View.Tile>|  
  
 Ключевое свойство <xref:System.Windows.Forms.ListView> элемент управления является <xref:System.Windows.Forms.ListView.Items%2A>, который содержит элементы, отображаемые элементом управления. <xref:System.Windows.Forms.ListView.SelectedItems%2A> Свойство содержит коллекцию элементов, выбранных в элементе управления. Пользователь может выбрать несколько элементов, например перетаскивание нескольких элементов за раз на другой элемент управления, если <xref:System.Windows.Forms.ListView.MultiSelect%2A> свойству `true`. <xref:System.Windows.Forms.ListView> Элемент управления может отображать флажки рядом с элементами, если <xref:System.Windows.Forms.ListView.CheckBoxes%2A> свойству `true`.  
  
 <xref:System.Windows.Forms.ListView.Activation%2A> Свойство определяет, какой тип действия должен выполнить пользователь для активации элемента в списке: возможные варианты: <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, и <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick> для активации требуется одним щелчком для активации элемента. <xref:System.Windows.Forms.ItemActivation.TwoClick> Активация требует от пользователя, дважды щелкните для активации элемента; одним щелчком мыши изменяет цвет текста элемента. <xref:System.Windows.Forms.ItemActivation.Standard> Активация требует от пользователя, дважды щелкните, чтобы активировать элемент, но элемент не приводит к изменению внешнего вида.  
  
 <xref:System.Windows.Forms.ListView> Управления также поддерживает стили оформления и другие функции, доступные на платформе Windows XP, включая группирование, мозаичное представление и метки вставки.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ListView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавить столбцы для элемента управления ListView в Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков для элемента управления ListView в Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение дополнительных данных в столбцы с помощью элемента управления ListView в Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Выберите элемент в элементе управления ListView формы Windows](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Практическое руководство. Группирование элементов в элементе управления ListView формы Windows](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Практическое руководство. Индикация в элементе управления ListView формы Windows](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Практическое руководство. Добавление возможностей поиска в элемент управления ListView](how-to-add-search-capabilities-to-a-listview-control.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Практическое руководство. Создание с несколькими областями пользовательского интерфейса с помощью Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
