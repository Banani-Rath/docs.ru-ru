---
title: "Оператор /= (Справочник по C#) | Microsoft Docs"
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
  - "/=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/= (оператор назначения деления) [C#]"
  - "оператор назначения деления (/=) [C#]"
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор /= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор назначения деления.  
  
## Заметки  
 Выражение, использующее оператор назначения `/=`, такое как  
  
```  
x /= y  
```  
  
 , эквивалентно выражению  
  
```  
x = x / y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  [Оператор \/](../../../csharp/language-reference/operators/division-operator.md) предопределен для числовых типов для выполнения деления.  
  
 Оператор `/=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \/](../../../csharp/language-reference/operators/division-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Для всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.  
  
## Пример  
 [!CODE [csRefOperators#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#5)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)