---
title: "Оператор / (Справочник по C#) | Microsoft Docs"
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
  - "/_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/ - оператор [C#]"
  - "оператор деления [C#]"
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор / (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор деления \(`/`\) Делит первый операнд вторым операндом.  Все числовые типы имеют предопределенные операторы деления.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `/` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Перегрузка оператора `/` явно вызывает перегрузку [оператора \/\=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md).  
  
 При делении двух целых чисел результат всегда является целочисленным.  Например результат выражения 7 \/ 3 равняется 2.  Чтобы определить остаток 7 \/ 3, используйте оператор остатка \([%](../../../csharp/language-reference/operators/modulus-operator.md)\).  Чтобы получить частное в виде рационального числа или дроби, присвойте делителю или делимому тип `float` или `double`.  Можно присвоить тип неявно express делимое или делитель в десятичном виде, помещая цифры справа от десятичной запятой, как показано в следующем примере.  
  
## Пример  
 [!CODE [csRefOperators#42](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#42)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)