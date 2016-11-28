---
title: "Практическое руководство. Сохранение результатов запроса в памяти (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "хранилище результатов запроса LINQ [LINQ в C#]"
  - "выражения запросов [LINQ в C#], сохранение результатов"
ms.assetid: 7271597f-3523-4f7b-b088-1eeffe913b2d
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Сохранение результатов запроса в памяти (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Запрос, по сути своей является набором инструкций, на основании которых осуществляется извлечение и организация данных.  Для выполнения запроса требуется вызов его метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.  Этот вызов выполняется при использовании цикла `foreach` для итерации элементов.  Для оценки запроса и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.  
  
## Пример  
 [!CODE [csProgGuideLINQ#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#25)]  
  
## Компиляция кода  
  
-   Создайте проект [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)], предназначенный для платформы .NET Framework версии 3.5.  По умолчанию в проекте имеются ссылка на файл System.Core.dll и директива `using` \(C\#\) для пространства имен System.Linq.  
  
-   Скопируйте код в созданный проект.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить программу.  
  
-   Нажмите любую клавишу для выхода из окна консоли.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)