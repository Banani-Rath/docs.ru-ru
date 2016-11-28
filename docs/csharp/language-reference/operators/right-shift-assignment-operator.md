---
title: "Оператор &gt;&gt;= (Справочник по C#) | Microsoft Docs"
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
  - ">>=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">>= - оператор (назначение сдвига вправо) [C#]"
  - "оператор назначения сдвига вправо (>>=) [C#]"
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор &gt;&gt;= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор присваивания сдвига вправо.  
  
## Заметки  
 Выражение формы  
  
```  
x >>= y  
```  
  
 вычисляется как  
  
```  
x = x >> y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  [Оператор \>\>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на значение, заданное `y`.  
  
 Оператор \>\>\= нельзя перегрузить непосредственно, однако определенные пользователем типы могут перегрузить [оператор \>\>](../../../csharp/language-reference/operators/right-shift-operator.md) \(см.[оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!CODE [csRefOperators#11](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#11)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)