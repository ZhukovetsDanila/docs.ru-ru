---
title: Оператор ^= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: efea38d7da13b67490f498658e7739929517dba2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964949"
---
# <a name="-operator-visual-basic"></a>Оператор ^= (Visual Basic)
Возводит значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любой числовой переменной или свойства.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `^=` оператор может быть простой скалярной переменной, свойства или элемента массива. Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `^=` Оператор прежде всего создает значение переменной или свойства (в левой части оператора) в степень значения выражения (в области справа от оператора). Затем оператор присваивает результат этой операции переменной или свойству.  
  
 Visual Basic всегда выполняет возведение в степень в [тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md). Операнды любого другого типа преобразуются в `Double`, и результат всегда имеет `Double`.  
  
 Значение `expression` может быть дробным, отрицательным или оба.  
  
## <a name="overloading"></a>Перегрузка  
 [^ Оператор](../../../visual-basic/language-reference/operators/exponentiation-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `^` оператор влияет на поведение `^=` оператор. Если код использует `^=` для класса или структуры, перегружающей `^`, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `^=` оператор для вызова значении, равном единице `Integer` переменной в степень второй переменной и назначает полученное значение первой переменной.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>См. также
- [Оператор ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
