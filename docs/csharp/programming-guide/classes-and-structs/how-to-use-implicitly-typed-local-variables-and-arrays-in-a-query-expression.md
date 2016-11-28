---
title: "Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса (Руководство по программированию в C#) | Microsoft Docs"
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
  - "неявно типизированные локальные переменные [C#], использование"
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно использовать неявно типизированные локальные переменные всякий раз при определении компилятором типа локальной переменной.  Для хранения анонимных типов, часто используемых в выражениях запросов, необходимо использовать неявно типизированные локальные переменные.  Далее представлены примеры требуемого и необязательного применений неявно типизированных локальных переменных в запросах.  
  
 Объявление неявно типизированных локальных переменных осуществляется с помощью контекстного ключевого слова [var](../../../csharp/language-reference/keywords/var.md).  Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Пример  
 В следующем примере показан общий сценарий, в котором необходимо ключевое слово `var`: выражение запроса, создающее последовательность анонимных типов.  В данном сценарии требуется, чтобы переменная запроса и переменная итерации в операторе `foreach` были неявно типизированы с помощью `var`, поскольку доступ к имени типа для анонимного типа закрыт.  Дополнительные сведения об анонимных типах см. в разделе [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!CODE [csProgGuideLINQ#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#32)]  
  
## Пример  
 В следующем примере описана сходная ситуация использования ключевого слова `var`, но при этом использование `var` необязательно.  Поскольку `student.LastName` является строкой, выполнение запроса возвращает последовательность строк.  В связи с этим тип `queryID` может быть объявлен как `System.Collections.Generic.IEnumerable<string>` вместо `var`.  Ключевое слово `var` используется для удобства.  В данном примере переменная итерации в операторе `foreach` явно типизирована как строка, но она может быть также объявлена при помощи ключевого слова `var`.  Поскольку тип переменной итерации не является анонимным типом, использование `var` необязательно.  Важно помнить, что само ключевое слово `var` является не типом, а инструкцией компилятору для определения и назначения типа.  
  
 [!CODE [csProgGuideLINQ#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#33)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)