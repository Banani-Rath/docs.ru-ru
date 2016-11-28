---
title: "if-else (Справочник по C#) | Microsoft Docs"
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
  - "if_CSharpKeyword"
  - "else"
  - "else_CSharpKeyword"
  - "if"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "else - ключевое слово [C#]"
  - "if - ключевое слово [C#]"
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# if-else (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `if` определяет, какой оператор будет выполняться при выполнения условия, заданного выражением `Boolean`. В приведенном ниже примере переменной `result` типа `Boolean` присваивается значение `true`, а затем она проверяется оператором `if`. В результате получается `The condition is true`.  
  
 [!CODE [csrefKeywordsSelection#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#1)]  
  
 Примеры в этом разделе можно выполнить, разместив их в методе `Main` консольного приложения.  
  
 Оператор `if` в С\# может иметь две формы, как показано в приведенном ниже примере.  
  
```c#  
  
// if-else statement if (condition) { then-statement; } else { else-statement; } // Next statement in the program. // if statement without an else if (condition) { then-statement; } // Next statement in the program.  
```  
  
 В операторе `if-else`, если `condition` имеет значение true, выполняется `then-statement`. Если `condition` имеет значение false, выполняется `else-statement`. Так как `condition` не может одновременно иметь значения true и false, `then-statement` и `else-statement` оператора `if-else` не могут выполняться оба. После выполнения `then-statement` или `else-statement` управление передается следующему оператору после оператора `if`.  
  
 В операторе `if`, не включающем оператор `else`, если `condition` имеет значение true, выполняется `then-statement`. Если `condition` имеет значение false, то управление передается следующему оператору после оператора `if`.  
  
 `then-statement` и `else-statement` могут состоять из одного или нескольких операторов, заключенных в фигурные скобки \(`{}`\). Для одного оператора скобки необязательны, но рекомендуются.  
  
 Оператор или операторы в `then-statement` и `else-statement` могут быть любого типа, включая другой оператор `if`, вложенный в исходный оператор `if`. Во вложенных операторах `if` каждое предложение `else` относится к последнему оператору `if`, у которого нет соответствующего объекта `else`. В приведенном ниже примере `Result1` получается, если оба выражения `m > 10` и `n > 20` имеют значение true. Если `m > 10` имеет значение true, но `n > 20` — значение false, то получается `Result2`.  
  
 [!CODE [csrefKeywordsSelection#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#2)]  
  
 Если вместо этого нужно, чтобы `Result2` получался, когда значение `(m > 10)` равно false, можно указать такую связь с помощью фигурных скобок для задания начала и конца вложенного оператора `if`, как показано в приведенном ниже примере.  
  
 [!CODE [csrefKeywordsSelection#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#3)]  
  
 `Result2` получается, если условие `(m > 10)` имеет значение false.  
  
## Пример  
 В приведенном ниже примере вы вводите символ с помощью клавиатуры, а программа использует вложенный оператор `if` для определения того, является ли введенный символ буквой. Если введенный символ является буквой, программа определяет его регистр. Для каждого случая предусмотрено отдельное сообщение.  
  
 [!CODE [csrefKeywordsSelection#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#4)]  
  
## Пример  
 Также можно поместить оператор `if` в блок else, как показано в части кода, приведенной ниже. В примере операторы `if` помещаются в два блока else и один блок then. Комментарии определяют какие условия выполняются в каждом из блоков.  
  
 [!CODE [csrefKeywordsSelection#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#5)]  
  
## Пример  
 В приведенном ниже примере определяется, является ли введенный символ строчной буквой, прописной буквой или цифрой. Если все три условия имеют значение false, то символ не является алфавитно\-цифровым. Для каждого случая выводится сообщение.  
  
 [!CODE [csrefKeywordsSelection#6](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#6)]  
  
 Точно так же как оператор в блоке else или блоке then может быть любым допустимым оператором, в качестве условия можно использовать любое допустимое логическое выражение. Вы можете использовать логические операторы, такие как [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) и [\!](../../../csharp/language-reference/operators/logical-negation-operator.md), для формирования составных условий. В коде ниже приведены примеры.  
  
```c#  
// NOT bool result = true; if (!result) { Console.WriteLine("The condition is true (result is false)."); } else { Console.WriteLine("The condition is false (result is true)."); } // Short-circuit AND int m = 9; int n = 7; int p = 5; if (m >= n && m >= p) { Console.WriteLine("Nothing is larger than m."); } // AND and NOT if (m >= n && !(p > m)) { Console.WriteLine("Nothing is larger than m."); } // Short-circuit OR if (m > n || m > p) { Console.WriteLine("m isn't the smallest."); } // NOT and OR m = 4; if (!(m >= n || m >= p)) { Console.WriteLine("Now m is the smallest."); } // Output: // The condition is false (result is true). // Nothing is larger than m. // Nothing is larger than m. // m isn't the smallest. // Now m is the smallest.  
```  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [?Оператор :](../../../csharp/language-reference/operators/conditional-operator.md)   
 [Оператор if\-else \(C\+\+\)](/visual-cpp/cpp/if-else-statement-cpp)   
 [switch](../../../csharp/language-reference/keywords/switch.md)