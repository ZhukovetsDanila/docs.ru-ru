---
title: LINQ to Objects (Visual Basic)
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: 87c804a831272b2a0c08ac85a552fec86d665e7f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185471"
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
Термин "LINQ to Objects" означает использование запросов LINQ с любой коллекцией <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> напрямую, без привлечения промежуточного поставщика LINQ, API [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) или [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md). Вы можете выполнить запрос LINQ к любой перечислимой коллекции, такой как <xref:System.Collections.Generic.List%601>, <xref:System.Array> или <xref:System.Collections.Generic.Dictionary%602>. Коллекция может быть определена пользователем или возвращена API .NET Framework.  
  
 В общем смысле LINQ to Objects представляет собой новый подход к коллекциям. Раньше нужно было написать сложные циклы `For Each`, определяющие порядок извлечения данных из коллекции. При использовании LINQ пишется декларативный код, описывающий, какие данные необходимо извлечь.  
  
 Кроме того, запросы LINQ предлагают три основных преимущества по сравнению с традиционными циклами `For Each`:  
  
1.  Они более краткие и удобочитаемые, особенно при фильтрации нескольких условий.  
  
2.  Они предоставляют широкие возможности фильтрации, упорядочивания и группировки с минимумом кода приложения.  
  
3.  Они могут переноситься в другие источники данных практически без изменений.  
  
 В общем, чем сложнее операция, которую нужно выполнить с данными, тем больше преимуществ вы получаете при использовании LINQ вместо традиционных способов итерации.  
  
 Целью этого раздела является демонстрация подхода LINQ с помощью нескольких примеров. Он не претендует на исчерпывающий характер.  
  
## <a name="in-this-section"></a>В этом разделе  
 [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 Использование LINQ для запроса и преобразования строк и коллекций строк. Ссылки на разделы, демонстрирующие эти принципы.  
  
 [LINQ и отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 Ссылки на пример, демонстрирующий, как LINQ использует отражение.  
  
 [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Использование LINQ для взаимодействия с файловыми системами. Ссылки на разделы, демонстрирующие эти понятия.  
  
 [Практическое: выполнение запроса к ArrayList с помощью LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Выполнение запроса ArrayList в C#.  
  
 [Практическое: Добавление настраиваемых методов для запросов LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Расширение набора методов, которые можно использовать для запросов LINQ путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Ссылки на разделы, рассказывающие LINQ и содержащие примеры кода выполнения запросов.
