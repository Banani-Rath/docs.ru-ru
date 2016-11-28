---
title: "explicit (Справочник по C#) | Microsoft Docs"
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
  - "explicit_CSharpKeyword"
  - "explicit"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "explicit - ключевое слово [C#]"
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# explicit (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `explicit` служит для объявления оператора преобразования пользовательского типа, который следует вызывать во время приведения.  Например, следующий оператор выполняет преобразование из класса Fahrenheit в класс Celsius.  
  
 [!CODE [csrefKeywordsConversion#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#2)]  
  
 Такой оператор можно вызвать следующим образом.  
  
 [!CODE [csrefKeywordsConversion#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#3)]  
  
 Оператор преобразования выполняет преобразование из исходного типа в тип назначения.  Оператор преобразования предоставляется исходным типом.  В отличие от неявного преобразования операторы явного преобразования вызываются с помощью приведения.  Если операция преобразования может вызвать исключения или потерю информации, необходимо пометить ее ключевым словом `explicit`.  Это позволит избежать скрытого вызова компилятором операции преобразования, которая может привести к непредсказуемым последствиям.  
  
 Если приведение пропустить, произойдет ошибка времени компиляции CS0266.  
  
 Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Пример  
 В следующем примере показаны классы `Fahrenheit` и `Celsius`, в каждом из которых определен оператор явного преобразования в другой класс.  
  
 [!CODE [csrefKeywordsConversion#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#1)]  
  
## Пример  
 В следующем примере определена структура `Digit`, представляющая один разряд.  Для преобразования типа `byte` в тип `Digit` определен оператор, но поскольку не все значения типа byte можно преобразовать в `Digit`, преобразование выполняется явным образом.  
  
 [!CODE [csrefKeywordsConversion#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsConversion#4)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [неявные](../../../csharp/language-reference/keywords/implicit.md)   
 [оператор](../../../csharp/language-reference/keywords/operator.md)   
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [Определяемые пользователем цепного явные преобразования в C\#](http://go.microsoft.com/fwlink/?LinkId=112384)