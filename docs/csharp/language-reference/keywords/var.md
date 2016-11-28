---
title: "var (справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "var"
  - "var_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "var - ключевое слово [C#]"
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# var (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Начиная с версии Visual C\# 3.0 объявляемые в области метода переменные могут иметь неявный тип `var`.  Локальная переменная с неявным типом имеет строгую типизацию, как если бы тип был задан явно, только тип определяет компилятор.  Следующие два объявления `i` функционально являются эквивалентами:  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## Пример  
 В следующем примере показано два выражения запроса.  В первом выражении использование типа `var` допустимо, но не обязательно, потому что тип результата запроса может быть задан явно как `IEnumerable<string>`.  Однако во втором выражении использование типа `var` обязательно, потому что результатом является коллекция анонимных типов и имя этого типа является доступным только для компилятора.  Обратите внимание, что в примере №2 `foreach` переменная итерации `item` должна также иметь неявный тип.  
  
 [!CODE [csrefKeywordsTypes#18](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#18)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)