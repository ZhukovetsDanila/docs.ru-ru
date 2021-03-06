---
title: Атрибуты
description: Узнайте, как F# атрибуты позволяют применять к программным конструкциям метаданные.
ms.date: 05/16/2016
ms.openlocfilehash: 34223523efbb3bd89bb73f35fac3dfd8113d8611
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611846"
---
# <a name="attributes"></a>Атрибуты

Атрибуты позволяют применять к программным конструкциям метаданные.

## <a name="syntax"></a>Синтаксис

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *целевой* является необязательным и, если он присутствует, указывает тип сущности программы, к которому применяется атрибут. Допустимые значения для *целевой* приведены в таблице, который приводится далее в этом документе.

*Имя атрибута* ссылается на (возможно полное с пространствами имен) имя допустимого атрибута типа, с или без суффикса `Attribute` , обычно используется в именах типов атрибутов. Например, тип `ObsoleteAttribute` может быть сокращено до `Obsolete` в данном контексте.

*Аргументы* аргументы в конструктор для типа атрибута. Если атрибут имеет конструктор по умолчанию, можно опустить список аргументов и круглые скобки. Атрибуты поддерживают позиционные аргументы и именованные аргументы. *Позиционные аргументы* являются аргументами, которые используются в порядке, в котором они появляются. Именованные аргументы можно использовать, если атрибут содержит открытые свойства. Можно задать с помощью следующего синтаксиса в списке аргументов.

```
*property-name* = *property-value*
```

Такие инициализации свойств можно в любом порядке, но они должны следовать позиционные аргументы. Ниже приведен пример атрибута, которые используются позиционные аргументы и инициализации свойств.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

В этом примере атрибут имеет `DllImportAttribute`, здесь используется в сокращенной форме. Первым аргументом является позиционным параметром, а второй — это свойство.

Атрибуты, конструкции программирования .NET, которая позволяет объект, известный как *атрибут* необходимо сопоставить с типом или других программных элементов. Элемент программы, к которому применяется атрибут называется *конечного объекта атрибута*. Атрибут обычно содержит метаданные о своей цели. В этом контексте метаданные могут быть любые данные о типе, отличные от его полей и членов.

Атрибуты в F# могут применяться к следующие программные конструкции: функции, методы, сборки, модули, типы (классы, записи, структуры, интерфейсы, делегаты, перечисления, объединения и т. д.), конструкторы, свойства, поля, параметры, введите параметры и возвращаемые значения. Атрибуты не допускаются в `let` привязки внутри классов, выражений и выражений рабочего процесса.

Как правило объявление атрибута появляется непосредственно перед объявлением конечного объекта атрибута. Несколько объявлений атрибутов можно использовать вместе, как показано ниже.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

Атрибуты во время выполнения можно запрашивать с помощью отражения .NET.

Можно объявить несколько атрибутов по отдельности, как показано в предыдущем примере, или можно объявлять их в один набор квадратных скобок при использовании точки с запятой для разделения отдельных атрибутов и конструкторов, как показано ниже.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

Обычно встречаются следующие атрибуты: `Obsolete` атрибутов, атрибуты для обеспечения безопасности, атрибуты для поддержки COM, атрибуты, относящиеся к владение кодом и атрибуты, указывающее, может ли быть сериализован тип. В следующем примере показано использование `Obsolete` атрибута.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Для целей атрибут `assembly` и `module`, можно применить атрибуты верхнего уровня `do` привязки сборки. Можно включить слово `assembly` или `module` в объявление атрибута, как показано ниже.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Если опустить конечного объекта атрибута для атрибута, применяемых к `do` привязки, F# компилятор пытается определить целевой объект атрибута, который лучше всего подходит для этого атрибута. Многие классы атрибутов имеют атрибут типа `System.AttributeUsageAttribute` , включает в себя сведения о возможных целевых объектах, поддерживаемых для этого атрибута. Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает функции в качестве целевых объектов, этот атрибут выбирается для применения к главную точку входа программы. Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает сборки в качестве целевых объектов, компилятор выбирает этот атрибут, чтобы применить к сборке. Большинство атрибутов не применяются к функции и сборок, но в случаях, когда это делается, этот атрибут выбирается для применения к главной функции программы. Если целевой атрибут указан явно, атрибут применяется для указанного целевого объекта.

Несмотря на то, что вы обычно не требуется указать целевой объект атрибута явным образом, допустимые значения для *целевой* в атрибуте показаны в следующей таблице, а также примеры использования.

<table>
  <tr>
    <th>Целевой атрибут</td>
    <th>Пример</td> 
  </tr>
  <tr>
    <td>сборка</td>
    <td>`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</td> 
  </tr>
  <tr>
    <td>return</td>
    <td>"функция1 let x: [<return: Obsolete>] int = x + 1"</td> 
  </tr>
  <tr>
    <td>поле</td>
    <td>"[<field: DefaultValue>] val изменяемый x: int"</td> 
  </tr>
  <tr>
    <td>свойство;</td>
    <td>"[<property: Obsolete>] это. MyProperty = x "</td> 
  </tr>
  <tr>
    <td>param</td>
    <td>"член это. MyMethod ([<param: Out>] x: ref<int>) = x: = 10".</td> 
  </tr>
  <tr>
    <td>type</td>
    <td>

        ```
        [<type: StructLayout(Sequential)>] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        ```
    </td> 
  </tr>
</table>

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)