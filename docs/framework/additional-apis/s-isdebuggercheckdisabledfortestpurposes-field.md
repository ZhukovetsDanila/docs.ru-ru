---
title: s_isDebuggerCheckDisabledForTestPurposes Field
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: b6490919163a7c4a618bf9a8d0e2aa145f60eda1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372312"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes Field

Это частное поле в `System.Windows.Diagnostics.VisualDiagnostics` класс используется средой Visual Studio, чтобы определить, будет ли выполняться внутренняя проверка для активного отладчика.

## <a name="syntax"></a>Синтаксис

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> API-интерфейсы в `System.Windows.Diagnostics.VisualDiagnostics` класса доступны только в случае, когда приложение выполняется в режиме отладки. Задайте `s_isDebuggerCheckDisabledForTestPurposes` для `true` для доступа к API вне отладчика.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Windows.Diagnostics>

**Сборка:** PresentationCore (в PresentationCore.dll)

**Версии платформы .NET framework:** Доступно с версии 4.6.