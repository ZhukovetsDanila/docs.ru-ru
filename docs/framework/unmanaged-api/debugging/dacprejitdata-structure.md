---
title: Структура DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 974b99da085a5cb969ab37cddb0f2f2c62010d14
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828689"
---
# <a name="dacprejitdata-structure"></a>Структура DacpReJitData

Определяет основные сведения о данный метод инструментированного профилировщиком.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a>Участники

| Член           | Описание:                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | Номер редакции ReJit для метода.                                                          |
| `flags`          | Флаг, указывающий текущее состояние метода инструментарий ReJit для данной версии. |
| `NativeCodeAddr` | Базовый адрес rejitted реализацию метода.                                         |


## <a name="remarks"></a>Примечания

Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек. Чтобы использовать его, определите структуру, как указано выше. Структуры также должен быть определен с помощью `ms_struct` упаковки в противном случае с помощью компиляторов Microsoft.

## <a name="requirements"></a>Требования
**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
