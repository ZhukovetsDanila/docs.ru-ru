---
title: Команда dotnet nuget delete
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 827d295d7a52b6c9c82adbcf3d25281bd1cc98fd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168316"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a>Описание

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка. Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.

## <a name="arguments"></a>Аргументы

* **`PACKAGE_NAME`**

  Имя/идентификатор удаляемого пакета.

* **`PACKAGE_VERSION`**

  Версия удаляемого пакета.

## <a name="options"></a>Параметры

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

* **`--force-english-output`**

  Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`--interactive`**

  Позволяет блокировать команду до выполнения действия пользователем, например аутентификации. Параметр доступен, начиная с пакета SDK для .NET Core 2.2.

* **`-k|--api-key <API_KEY>`**

  Ключ API для сервера.

* **`--no-service-endpoint`**

  Не добавляет "api/v2/package" в исходный URL-адрес. Параметр доступен, начиная с пакета SDK для .NET Core 2.1.

* **`--non-interactive`**

  Не запрашивает у пользователя данные или подтверждения.

* **`-s|--source <SOURCE>`**

  Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

* **`--force-english-output`**

  Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`-k|--api-key <API_KEY>`**

  Ключ API для сервера.

* **`--non-interactive`**

  Не запрашивает у пользователя данные или подтверждения.

* **`-s|--source <SOURCE>`**

  Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

---

## <a name="examples"></a>Примеры

* Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```