---
title: "Оператор ^ (Справочник по C#) | Microsoft Docs"
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
  - "^_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^ - оператор [C#]"
  - "оператор побитового исключающего OR [C#]"
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор ^ (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Бинарные операторы `^` являются предопределенными для целых типов и `bool`.  Для целых типов оператор `^` выполняет побитовую операцию исключающего OR его операндов.  Для операндов `bool` оператор `^` выполняет операцию логического исключающего OR операндов, то есть результатом будет являться значение `true` только в том случае, если ровно один из его операндов имеет значение `true`.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `^` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!CODE [csRefOperators#30](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#30)]  
  
 При вычислении выражения `0xf8 ^ 0x3f` в предыдущем примере выполняется операция побитового исключающего ИЛИ с двумя двоичными значениями, которые соответствуют шестнадцатеричным значениям F8 и 3F:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 Результат исключающего ИЛИ равен значению `1100 0111`, или C7 в шестнадцатеричной системе.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)