---
title: "Операторы преобразования (Руководство по программированию в C#) | Microsoft Docs"
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
  - "язык C#, операторы преобразования"
  - "операторы преобразования [C#]"
  - "операторы [C#], преобразование"
  - "заданные пользователем преобразования [C#]"
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Операторы преобразования (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\# позволяет разработчикам объявлять операции преобразования классов или структур, делая тем самым возможным преобразование одних классов и структур в другие, а также в базовые типы или из них.  Для задания преобразования используются операторы, называемые в соответствии с типом, к которому выполняется преобразование.  Преобразуемый аргумент или результат преобразования \(но не оба из них\) должны принадлежать к содержащему типу.  
  
 [!CODE [csProgGuideStatements#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#10)]  
  
## Общие сведения об операторах преобразования  
 Операторы преобразования обладают следующими свойствами.  
  
-   Преобразования, определенные как `implicit`, выполняются автоматически, если это требуется.  
  
-   Для выполнения преобразований, определенных как `explicit`, требуется вызов операции приведения.  
  
-   Все преобразования должны быть объявлены как `static`.  
  
## Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [явные](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [неявные](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [статический](../../../csharp/language-reference/keywords/static.md)  
  
## См. также  
 <xref:System.Convert>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Прикованные определяемых пользователем явные преобразования в C\#](http://go.microsoft.com/fwlink/?LinkId=112384)