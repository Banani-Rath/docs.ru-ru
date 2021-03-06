---
title: "Платформы и целевые объекты"
description: "Описание основных понятий целевых объектов платформы при написании кода .NET."
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 09/19/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
translationtype: Human Translation
ms.sourcegitcommit: 38561c2d25c6950d166bf706f4306c867e683b04
ms.openlocfilehash: 82ba6f4abe200dc48158eac1ad3e3609feeda2c9

---

# <a name="frameworks-and-targets"></a>Платформы и целевые объекты

Экосистема .NET основана на концепции платформ. Платформы определяют API, который можно использовать для ориентации на конкретную платформу. Одна из таких платформ — .NET Framework 4.6. Платформы используются в Visual Studio и других интегрированных средах разработки и редакторах для предоставления правильного набора API. Они также используются NuGet для создания и применения пакетов NuGet. Это позволяет обеспечить создание и использование подходящих пакетов (и базовых ресурсов) для целевой платформы. Платформы являются одним из ключевых элементов в экосистеме .NET. Эта концепция позволяет обеспечить правильность работы, предотвращая появление исключения @System.MissingMethodException и аналогичных исключений во время выполнения.

## <a name="framework-versions"></a>Версии платформ

Приведенная ниже таблица описывает набор платформ, которые можно использовать, указывая их названия, способы ссылки на них, а также версию [библиотеки .NET Standard](library.md), которую они реализуют.

| Платформа | Последняя версия | Моникер целевой платформы (TFM) | Компактный моникер целевой платформы (TFM) | Версия .NET Standard | Метапакет |
|:--------: | :--: | :--: | :--: | :--: | :--: | :--: |
| .NET Standard | 1.6 | .NETStandard,Version=1.6 | netstandard1.6 | Н/Д | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library)|
| Приложение .NET Core | 1.0.1 | .NETCoreApp,Version=1.0 | netcoreapp1.0 | 1.6 | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App)|
| .NET Framework | 4.6.2 | .NETFramework,Version=4.6.2 | net462 | 1.5 | Н/Д |

> [!NOTE]
> Эти версии платформ являются последними стабильными версиями. Могут также существовать и предварительные версии, которые не указаны в данной таблице.

## <a name="writing-about-frameworks"></a>Записи о платформах

Существует несколько способов сослаться на платформы в письменной форме, и большинство из них используется в данной документации. Приведенными ниже сведениями следует руководствоваться как при изучении имеющейся документации, так и при составлении новых документов.

Если взять платформу .NET Framework 4.6.1 в качестве примера, можно использовать следующие формы:

**Ссылка на продукт**

Можно ссылаться на среду выполнения или платформу .NET.

- ".NET Framework 4.6.1"

**Ссылка на платформу**

Можно ссылаться на платформу или ориентацию на нее с помощью длинных или коротких форм моникера целевой платформы. В общем случае допустимыми являются оба варианта.

- `.NETFramework,Version=4.6.1`
- `net461`

**Ссылка на семейство платформ**

Можно ссылаться на семейство платформ с помощью длинных или коротких форм идентификатора платформы. В общем случае допустимыми являются оба варианта.

- `.NETFramework`
- `net`



<!--HONumber=Nov16_HO3-->


