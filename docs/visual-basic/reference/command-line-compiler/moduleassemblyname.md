---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a16dd616c8a38dea4bd1779e4feea779b3a18e2d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375302"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Задает имя сборки, частью которой будет этот модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`assembly_name`|Имя сборки, которая будет частью данный модуль.|  
  
## <a name="remarks"></a>Примечания  
 Компилятор выполняет `-moduleassemblyname` только если параметр `-target:module` был указан параметр. В этом случае компилятор для создания модуля. Модуль, созданный компилятором допустим только для сборки, указанной в `-moduleassemblyname` параметр. Если вы поместите модуль в другой сборке, возникнут ошибки времени выполнения.  
  
 `-moduleassemblyname` Параметр требуется только в том случае, при выполнении следующих условий:  
  
-   Тип данных в модуле необходим доступ к `Friend` тип в сборке, на которую указывает ссылка.  
  
-   Свойства ссылки был предоставлен доступ к дружественной сборке на сборку, в которую будет встроен модуль.  
  
 Дополнительные сведения о создании модуля см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Дополнительные сведения о дружественных сборок, см. в разделе [дружественных сборок](../../../standard/assembly/friend-assemblies.md).  
  
> [!NOTE]
>  `-moduleassemblyname` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Создание многофайловой сборки](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-ссылке (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Дружественные сборки](../../../standard/assembly/friend-assemblies.md)
