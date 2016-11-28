---
title: "Практическое руководство. Создание нового метода для перечисления (Руководство по программированию в C#) | Microsoft Docs"
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
  - "расширяемость перечислений [C#]"
  - "перечисления [C#]"
  - "методы расширения [C#], для перечислений"
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание нового метода для перечисления (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Методы расширения можно использовать для добавления функций, соответствующих определенному типу перечисления.  
  
## Пример  
 В следующем примере перечисление `Grades` представляет возможные буквенные оценки, которые учащийся может получить в классе.  Метод расширения `Passing` добавлен к типу `Grades`, чтобы каждый экземпляр этого типа теперь "знал", представляет ли он проходную оценку или нет.  
  
 [!CODE [csProgGuideExtensionMethods#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideExtensionMethods#2)]  
  
 Обратите внимание, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, и что возвращаемое значение метода расширения отражает текущее значение этой переменной.  Это показывает, что система напрямую вызывает методы расширения в статическом классе, в котором они определяются.  
  
## Компиляция кода  
 Для выполнения этого кода скопируйте его в проект консольного приложения на языке Visual C\#, которое было создано в среде разработки [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)].  По умолчанию этот проект предназначен для версии 3.5 платформы [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и имеет ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq.  Если одно или более требований в проекте отсутствуют, их можно добавить вручную.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)