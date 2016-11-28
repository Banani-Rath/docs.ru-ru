---
title: "switch (Справочник по C#) | Microsoft Docs"
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
  - "switch_CSharpKeyword"
  - "switch"
  - "case"
  - "case_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "switch - оператор [C#]"
  - "switch - ключевое слово [C#]"
  - "case - оператор [C#]"
  - "default - ключевое слово [C#]"
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
caps.handback.revision: 47
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# switch (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Выражение `switch` — это оператор управления, выбирающий *раздел switch* для выполнения из списка кандидатов.  
  
 Оператор `switch` включает один или несколько разделов switch.  Каждый раздел switch содержит одну или несколько *меток case*, за которыми следует один или несколько операторов.  В следующем примере показан простой оператор `switch` с тремя разделами switch.  Каждый раздел switch содержит одну метку case, например `case 1`, и два оператора.  
  
 [!CODE [csrefKeywordsSelection#7](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#7)]  
  
## Заметки  
 В каждой метке case указывается постоянное значение.  Оператор switch передает управление тому разделу, метка case которого совпадает со значением *выражение switch* \(`caseSwitch` в этом примере\).  Если метка case не содержит соответствующего значения, управление передается в раздел `default`, если таковой имеется.  Если раздела `default` нет, никакие действия не выполняются и управление передается за пределы оператора `switch`.  В предыдущем примере, выполняются операторы в первом разделе switch, поскольку `case 1` совпадает со значением `caseSwitch`.  
  
 Оператор `switch` может содержать любое количество разделов switch, а каждый раздел может иметь одну или несколько меток case \(как показано в этом примере ниже\).  Однако две метки case не могут содержать одно и то же постоянное значение.  
  
 Выполнение списка операторов в выбранном разделе switch начинается с первого оператора и продолжается по списку, обычно до достижения оператора перехода, такого как `break`, `goto case`, `return` или `throw`.  В этой точке управление передается за пределы оператора `switch` или к другой метке case.  
  
 В отличие от C\+\+, C\# не позволяет продолжить выполнение следующего раздела switch после выполнения предыдущего раздела.  Приведенный ниже код вызывает ошибку.  
  
```c#  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
  
 Согласно требованиям C\# конец разделов switch, включая последний раздел, должен быть недостижим.  То есть, в отличие от некоторых языков, выполнение не может переходить на следующий раздел switch.  Хотя это требование обычно выполняется с помощью оператора `break`, допустим также следующий вариант, поскольку он гарантирует, что конец списка операторов не будет достигнут.  
  
```c#  
case 4:  
    while (true)  
        Console.WriteLine("Endless looping. . . .");  
```  
  
## Пример  
 В следующем примере показаны требования и возможности оператора `switch`.  
  
 [!CODE [csrefKeywordsSelection#9](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#9)]  
  
## Пример  
 В последнем случае поток выполнения контролируется строковой переменной `str` и строковыми метками case.  
  
 [!CODE [csrefKeywordsSelection#8](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#8)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор switch \(C\+\+\)](/visual-cpp/cpp/switch-statement-cpp)   
 [if\-else](../../../csharp/language-reference/keywords/if-else.md)