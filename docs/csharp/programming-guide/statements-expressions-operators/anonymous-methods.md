---
title: "Анонимные методы (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "анонимные методы [C#]"
  - "делегаты [C#], анонимные методы"
  - "методы [C#], анонимные"
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Анонимные методы (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) были единственным способом объявления [делегата](../../../csharp/language-reference/keywords/delegate.md) в версиях C\#, предшествующих версии 2.0.  Анонимные методы были представлены в C\# 2.0, а в версиях C\# 3.0 и более поздних лямбда\-выражения заменяют эти методы и являются предпочтительным способом написания встроенного кода.  Однако сведения об анонимных методах, представленные в данном разделе, применяются и к лямбда\-выражениям.  Существует только один случай, в котором функциональность анонимного метода отсутствует в лямбда\-выражениях.  Анонимные методы позволяют отказаться от использования списка параметров.  Это означает, что анонимный метод может быть преобразован в делегаты с различными сигнатурами.  Это невозможно в ситуации с лямбда\-выражениями.  Дополнительные сведения именно о лямбда\-выражениях см. в разделе [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Создание анонимных методов является, по существу, способом передачи блока кода в качестве параметра делегата.  Два примера:  
  
 [!CODE [csProgGuideDelegates#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#6)]  
  
 [!CODE [csProgGuideDelegates#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#5)]  
  
 Использование анонимных методов позволяет сократить издержки на кодирование при создании делегатов, поскольку не требуется создавать отдельный метод.  
  
 Например, указание блока кода вместо делегата может быть целесообразно в ситуации, когда создание метода может показаться ненужным действием.  Хорошим примером является запуск нового потока.  Этот класс создает поток и содержит код, выполняемый потоком без создания дополнительного метода для его делегата.  
  
 [!CODE [csProgGuideDelegates#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#7)]  
  
## Заметки  
 Областью действия параметров анонимного метода является *блок анонимного метода*.  
  
 Если целевой объект находится вне блока, то наличие оператора перехода, например [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) или [continue](../../../csharp/language-reference/keywords/continue.md), в блоке анонимного метода будет ошибкой.  Если целевой объект находится внутри блока, то наличие оператора перехода, например `goto`, `break` или `continue`, вне блока анонимного метода также будет ошибкой.  
  
 Локальные переменные и параметры, область действия которых содержит объявление анонимного метода, называются *внешними* переменными анонимного метода.  Например, в следующем сегменте кода `n` является внешней переменной.  
  
 [!CODE [csProgGuideDelegates#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#8)]  
  
 Ссылка на внешнюю переменную `n` считается  *захваченного* при создании делегата.  В отличие от локальных переменных жизни перехваченной переменной расширяет пока делегаты, ссылающиеся на анонимные методы мусор.  
  
 Анонимный метод не может обращаться к параметрам [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md) внешней области действия.  
  
 В *блоке анонимного метода* нельзя получить доступ ни к одному небезопасному коду.  
  
 Анонимные методы не разрешены с левой стороны оператора [is](../../../csharp/language-reference/keywords/is.md).  
  
## Пример  
 В следующем примере представлено два способа создания делегата.  
  
-   Связывание делегата с анонимным методом.  
  
-   Связывание делегата с именованным методом \(`DoWork`\).  
  
 В каждом случае при вызове делегата отображается сообщение.  
  
 [!CODE [csProgGuideDelegates#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#4)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Делегаты с именованными методами и делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)