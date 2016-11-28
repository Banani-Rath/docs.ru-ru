---
title: "Оператор %= (Справочник по C#) | Microsoft Docs"
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
  - "%=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "%= - оператор назначения (назначение модуля) [C#]"
  - "оператор назначения модуля (=%) [C#]"
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор %= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор присваивания остатка.  
  
## Заметки  
 Выражение, в котором используется оператор назначения `%=`, например  
  
```  
x %= y  
```  
  
 , эквивалентно выражению  
  
```  
x = x % y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  Оператор [%](../../../csharp/language-reference/operators/modulus-operator.md) предопределен для числовых типов для вычисления остатка от деления.  
  
 Оператор `%=` нельзя перегрузить непосредственно, однако определенные пользователем типы могут перегрузить [оператор %](../../../csharp/language-reference/operators/modulus-operator.md) \(см. [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!CODE [csRefOperators#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#4)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)