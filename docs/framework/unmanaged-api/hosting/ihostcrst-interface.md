---
title: Интерфейс IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34a911668db09b255282833cec3e6272b315373b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618663"
---
# <a name="ihostcrst-interface"></a>Интерфейс IHostCrst
Служит в качестве представления главного приложения из критических секций для управления потоками.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Enter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Войдет в критический раздел.|  
|[Метод Leave](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Оставляет критический раздел.|  
|[Метод SetSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Задает счетчик прокруток для критической секции.|  
|[Метод TryEnter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Пытается ввести критическую секцию и возвращает успех или сбой немедленно.|  
  
## <a name="remarks"></a>Примечания  
 `IHostCrst` позволяет общеязыковой среды выполнения (CLR) для взаимодействия непосредственно с представлением хоста критическую секцию, а не с помощью функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
