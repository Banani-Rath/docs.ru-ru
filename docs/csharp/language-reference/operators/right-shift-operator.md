---
title: "Оператор &gt;&gt; (Справочник по C#) | Microsoft Docs"
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
  - ">>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">> - оператор [C#]"
  - "оператор сдвига вправо (>>) [C#]"
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор &gt;&gt; (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор сдвига вправо \(`>>`\) сдвигает первый операнд вправо в соответствии с количеством бит, заданным вторым операндом.  
  
## Заметки  
 Если тип первого операнда — [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) \(32\-разрядное число\), начало сдвига задается пятью младшими разрядами второго операнда \(второй операнд & 0x1f\).  
  
 Если тип первого операнда — [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) \(64\-разрядное число\), начало сдвига задается пятью младшими разрядами второго операнда \(второй операнд & 0x3f\).  
  
 Если тип первого операнда — [int](../../../csharp/language-reference/keywords/int.md) или [long](../../../csharp/language-reference/keywords/long.md), сдвиг вправо является арифметическим сдвигом \(пустым старшим разрядам задан знаковый бит\).  Если тип первого операнда — [init](../../../csharp/language-reference/keywords/uint.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md), сдвиг вправо является логическим сдвигом \(старшие разряды заполняются нулями\).  
  
 Определенные пользователем типы могут вызвать перегрузку оператора `>>`; тип первого операнда должен быть определен пользователем, а тип второго должен быть [int](../../../csharp/language-reference/keywords/int.md).  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!CODE [csRefOperators#26](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#26)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)