---
title: "Оператор &gt;= (справочник по C#) | Microsoft Docs"
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
  - ">=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">= - оператор [C#]"
  - "больше или равно - оператор (>=) [C#]"
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор &gt;= (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Во всех числовых типах и типах перечислений определен оператор сравнения "больше или равно" \(`>=`\), который возвращает значение `true`, если первый операнд больше или равен второму, в противном случае возвращается значение `false`.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `>=`.  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Если оператор `>=` перегружен, то оператор [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) тоже должен быть перегружен.  Операции над целыми типами обычно разрешены в перечислениях.  
  
## Пример  
 [!CODE [csRefOperators#39](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#39)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)