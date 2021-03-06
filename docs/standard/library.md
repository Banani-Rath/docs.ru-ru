---
title: "Библиотека .NET Standard"
description: "Библиотека .NET Standard"
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
translationtype: Human Translation
ms.sourcegitcommit: f9ffbb2e300df2080276096095a7269736260ba1
ms.openlocfilehash: d56ddc264d861081f0b808711cccd489a374c0b8

---

# <a name="net-standard-library"></a>Библиотека .NET Standard

Библиотека .NET Standard представляет собой формальную спецификацию интерфейсов API .NET, которые должны быть доступны во всех средах выполнения .NET. Целью введения библиотеки Standard является повышение уровня согласованности экосистемы .NET. [ECMA 335](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) продолжает обеспечивать единообразие для среды выполнения .NET, однако аналогичные спецификации для библиотек базовых классов (BCL) .NET для реализаций библиотек .NET отсутствуют. 

Библиотека .NET Standard обеспечивает следующие ключевые сценарии: 

- Определяет унифицированный набор API-интерфейсов BCL для реализации всеми платформами .NET независимо от рабочей нагрузки.
- Позволяет разработчикам создавать переносимые библиотеки, которые могут использоваться в разных средах выполнения .NET, с помощью одного набора API-интерфейсов.
- Позволяет сократить или полностью устранить условную компиляцию общего источника из-за API-интерфейсов .NET (только для API операционной системы).

Различные среды выполнения .NET реализуют конкретные версии библиотеки .NET Standard. Каждая версия среды выполнения .NET ориентирована на использование максимальной поддерживаемой ею версии .NET Standard. Это также означает, что она поддерживает и предыдущие версии. Например, платформа .NET Framework 4.6 реализует библиотеку .NET Standard 1.3 и поэтому предоставляет все API-интерфейсы, определенные в библиотеке .NET Standard версий с 1.0 до 1.3. Аналогичным образом платформа .NET Framework 4.6.2 реализует библиотеку .NET Standard 1.5, а .NET Core 1.0 — библиотеку .NET Standard 1.6.

## <a name="net-platforms-support"></a>Поддержка платформ .NET

Ниже приведен полный набор сред выполнения .NET, поддерживающих библиотеку .NET Standard.

| Имя платформы | Alias |  |  |  |  |  | | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|.NET Standard | netstandard | 1,0 | 1.1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 | 2.0 |
|.NET Core|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1,0|vNext|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|vNext|4.6.1|
|Платформы Mono и Xamarin||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|vNext|
|Универсальная платформа Windows |uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|&rarr;|&rarr;|vNext|
|Windows|win|&rarr;|8.0|8.1||||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1||||||
|Windows Phone Silverlight|wp|8.0||||||||

## <a name="comparison-to-portable-class-libraries"></a>Сравнение с переносимыми библиотеками классов

Библиотеку .NET Standard можно рассматривать как новое поколение [переносимых библиотек классов (PCL)](https://msdn.microsoft.com/library/gg597391.aspx). Библиотека .NET Standard расширяет возможности создания переносимых библиотек, контролируя стандартную библиотеку BCL и обеспечивая повышенную согласованность разных сред выполнения .NET. Библиотека, нацеленная на библиотеку .NET Standard, является библиотекой PCL или "основанной на стандартах библиотекой PCL .NET". Существующие библиотеки PCL представляют собой "PCL на основе профиля".

Библиотека .NET Standard и профили PCL созданы для схожих целей, однако имеют существенные отличия.

Сходства:

- Определяет API-интерфейсы, которые можно использовать для совместного использования двоичного кода.

Различия:

- Библиотека .NET Standard является проверенным набором API, а профили PCL определяются пересечениями существующих платформ.
- Библиотека .NET Standard имеет линейно возрастающие версии, чего нет в профилях PCL.
- Профили PCL представляют платформы Майкрософт, а библиотека .NET Standard не зависит от платформы.

## <a name="specification"></a>Спецификация

Спецификация библиотеки .NET Standard представляет собой стандартизированный набор API. Она обслуживается реализаторами среды выполнения .NET, в частности корпорацией Майкрософт (включая .NET Framework, .NET Core и Mono) и Unity. При создании новых версий библиотеки .NET Standard используется процесс открытой обратной связи.

### <a name="official-artifacts"></a>Официальные артефакты

Официальная спецификация — это набор файлов с расширением CS, которые определяют API, являющиеся частью стандарта. [Справочный каталог](https://github.com/dotnet/corefx/tree/master/src/System.Runtime/ref) для каждого [компонента](https://github.com/dotnet/corefx/tree/master/src) определяет API библиотеки .NET Standard. Хотя справочные артефакты находятся в [репозитории CoreFX](https://github.com/dotnet/corefx), они не относятся непосредственно к .NET Core.

Метапакет [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([источник](https://github.com/dotnet/corefx/blob/master/pkg/NETStandard.Library/NETStandard.Library.packages.targets)) описывает набор библиотек, определяющих (частично) одну или несколько версий библиотеки .NET Standard.

Отдельный компонент, например System.Runtime, описывает следующее:

- Часть библиотеки .NET Standard (только область действия).
- Несколько версий библиотеки .NET Standard для данной области.

Доступны производные артефакты, упрощающие чтение и реализующие определенные сценарии для разработчика (например, использование компилятора).

- Список API с разметкой (подлежит определению)
- Ссылочные сборки, распространяемые в виде [пакетов NuGet](../core/packages.md) и указанные в ссылках метапакета [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Представление пакетов

Основным средством распространения ссылочных сборок библиотеки .NET Standard являются [пакеты NuGet](../core/packages.md). Соответствующие реализации будут предоставлены различными способами, наиболее уместными для каждой среды выполнения .NET.

Пакеты NuGet нацелены на одну или несколько [платформ](frameworks.md). Пакеты библиотеки .NET Standard нацелены на платформу ".NET Standard". Ориентироваться на платформу .NET Standard можно с помощью [компактного моникера целевой платформы](frameworks.md) `netstandard` (например, `netstandard1.4`). Библиотеки, предназначенные для запуска в различных средах выполнения, должны быть нацелены на эту платформу. 

Метапакет `NETStandard.Library` ссылается на полный набор пакетов NuGet, определяющих библиотеку .NET Standard.  Наиболее распространенным способом нацеливания на `netstandard` является ссылка на этот метапакет. Он описывает и предоставляет доступ примерно к 40 библиотекам .NET и связанным интерфейсам API, которые определяют библиотеку .NET Standard. Вы можете ссылаться на другие пакеты, предназначенные для `netstandard`, чтобы получить доступ к дополнительным интерфейсам API. 

### <a name="versioning"></a>Управление версиями

Данная спецификация имеет не единичный характер. Она является постепенно расширяемым набором API с линейно возрастающими номерами версий. Первая версия стандарта устанавливает базовый набор API. Последующие версии добавляют API и наследуют API, определенные в предыдущих версиях. Не существует установленных процедур для удаления API из стандарта.

Библиотека .NET Standard не относится к какой-либо одной среде выполнения .NET, а также не соответствует схеме управления версиями для любой из них.

API, добавляемые в любую из сред выполнения (например, .NET Framework, .NET Core и Mono), можно рассматривать как кандидаты для добавления в спецификацию, особенно в том случае, если они носят фундаментальный характер. Новые [версии библиотеки .NET Standard](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/net-platform-standard.md#list-of-net-corefx-apis-and-their-associated-net-platform-standard-version) создаются на основе выпусков среды выполнения .NET, что позволяет использовать новые API из библиотеки PCL .NET Standard. Подробнее механизм управления версиями описан в разделе [Управление версиями .NET Core](../core/versions/index.md).

Управление версиями библиотеки .NET Standard имеет важное значение для работы. Зная версию библиотеки .NET Standard, можно использовать библиотеки, ориентированные на ту же самую или более низкую версию. Ниже описана процедура по использованию библиотек PCL библиотеки .NET Standard, связанных на ориентацией на библиотеку .NET Standard.

- Выберите версию библиотеки .NET Standard для вашей библиотеки PCL.
- Используйте библиотеки, которые зависят от той же или более низкой версии библиотеки .NET Standard.
- При обнаружении библиотеки, которая зависит от более поздней версии библиотеки .NET Standard, нужно либо использовать такую же версию, либо отказаться от использования этой библиотеки.

### <a name="pcl-compatibility"></a>Совместимость библиотек PCL

Библиотека .NET Standard совместима с подмножеством профили PCL. Каждая из версий 1.0, 1.1 и 1.2 библиотеки .NET Standard перекрывается с набором профилей PCL. Такое перекрытие было создано по двум причинам:

- Предоставление библиотекам PCL на основе .NET Standard права ссылаться на основанные на профилях PCL.
- Возможность упаковки основанных на профилях PCL в виде PCL на основе .NET Standard.

Совместимость основанных на профилях PCL обеспечивается за счет пакета NuGet [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility). Такая зависимость требуется при ссылке на пакеты NuGet, содержащие основанные на профилях PCL.

Основанные на профилях PCL, которые упакованы в виде `netstandard`, удобнее использовать, чем обычно упакованные PCL на основе профилей в project.json. Упаковка `netstandard` совместима с существующими пользователями.

Можно просмотреть набор профилей PCL, совместимых с .NET Standard: 

| Профиль | Версия платформы .NET Standard |
| ---------| --------------- |
| Переносимое подмножество .NET Profile7 (.NET Framework 4.5, Windows 8) | 1.1 |
| Переносимое подмножество .NET Profile31 (Windows 8.1, Windows Phone Silverlight 8.1)| 1,0 |
| Переносимое подмножество .NET Profile32 (Windows 8.1, Windows Phone 8.1) | 1.2 |
| Переносимое подмножество .NET Profile44 (.NET Framework 4.5.1, Windows 8.1) | 1.2 |
| Переносимое подмножество .NET Profile49 (.NET Framework 4.5, Windows Phone Silverlight 8) | 1,0 |
| Переносимое подмножество .NET Profile78 (.NET Framework 4.5, Windows 8, Windows Phone Silverlight 8) | 1,0 |
| Переносимое подмножество .NET Profile84 (Windows Phone 8.1, Windows Phone Silverlight 8.1) | 1,0 |
| Переносимое подмножество .NET Profile111 (.NET Framework 4.5, Windows 8, Windows Phone 8.1) | 1.1 |
| Переносимое подмножество .NET Profile151 (.NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1) | 1.2 |
| Переносимое подмножество .NET Profile157 (Windows 8.1, Windows Phone 8.1, Windows Phone Silverlight 8.1) | 1,0 |
| Переносимое подмножество .NET Profile259 (.NET Framework 4.5, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8) | 1,0 |

## <a name="targeting-net-standard-library"></a>Нацеливание на библиотеку .NET Standard

Вы можете [создавать библиотеки .NET Standard](../core/tutorials/libraries.md) с помощью сочетания платформы `netstandard` и метапакета NETStandard.Library. Вы можете ознакомиться с примерами [ориентации на библиотеку .NET Standard с помощью средств .NET Core](../core/packages.md).



<!--HONumber=Nov16_HO3-->


