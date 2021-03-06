---
title: Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c50cee530cab0d5d164d930678651f302ddc7f09
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980767"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
В отличие от событий ненастраиваемых `Custom Event` требует `As` предложение после имени события, которая явно задает тип делегата для события.  
  
 Обычные события могут быть определены с `As` предложение и явный тип делегата или списка параметров сразу после имени события.  
  
 **Идентификатор ошибки:** BC31122  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите делегат с такой же список параметров, как пользовательское событие.  
  
     Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, а затем соответствующий делегат будет следующим.  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2.  Замените список параметров пользовательского события с `As` предложение, определяющее тип делегата.  
  
     В примере `Custom Event` объявление можно переписать следующим образом.  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a>Пример  
 В этом примере объявляется `Custom Event` и указывает необходимые `As` предложение с типом делегата.  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a>См. также
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
