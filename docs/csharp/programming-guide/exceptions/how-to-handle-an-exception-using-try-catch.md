---
title: "Практическое руководство. Обработка исключений с помощью блока try-catch (Руководство по программированию на C#) | Microsoft Docs"
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
  - "обработка исключений [C#], блоки try/catch"
  - "исключения [C#], блоки try/catch"
  - "блоки try/catch [C#]"
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Обработка исключений с помощью блока try-catch (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Блок [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) предназначен для перехвата и обработки исключений, происходящих в исполняемом коде.  Некоторые исключения могут обрабатываться в блоке `catch`, и проблема решается без повторного создания исключения. Но в большинстве случаев на этом этапе можно только проверить, что создано подходящее исключение.  
  
## Пример  
 В этом примере <xref:System.IndexOutOfRangeException> не является наиболее подходящим исключением. Для данного метода больше подходит исключение <xref:System.ArgumentOutOfRangeException>, поскольку ошибка вызвана переданным методу параметром `index`.  
  
 [!CODE [csProgGuideExceptions#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideExceptions#5)]  
  
## Комментарии  
 Код, вызывающий исключение, находится в блоке `try`.  Инструкция `catch` помещается сразу после него, чтобы обрабатывать исключение `IndexOutOfRangeException`, если оно происходит.  В блоке `catch` исключение `IndexOutOfRangeException` обрабатывается, и вместо него создается более подходящее исключение `ArgumentOutOfRangeException`.  Чтобы вызывающий объект получил максимально подробную информацию, рекомендуется указать исходное исключение в качестве значения <xref:System.Exception.InnerException%2A> нового исключения.  Поскольку свойство <xref:System.Exception.InnerException%2A> [доступно только для чтения](../../../csharp/language-reference/keywords/readonly.md), его значение необходимо присваивать только в конструкторе нового исключения.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)