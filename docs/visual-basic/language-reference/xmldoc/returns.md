---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 670064084d3297a54b2860da3fe3acab00fa3ed8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469187"
---
# <a name="returns-visual-basic"></a>\<Возвращает > (Visual Basic)
Указывает возвращаемое значение свойства или функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Параметры  
 `description`  
 Описание возвращаемого значения.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<returns>` тег в комментариях к объявлению метода для описания возвращаемого значения.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<returns>` тег, чтобы объяснить, что `DoesRecordExist` возврата функции.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
