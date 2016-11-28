---
title: "typeof (справочник по C#) | Microsoft Docs"
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
  - "typeof"
  - "typeof_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "typeof - ключевое слово [C#]"
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# typeof (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для получения объекта `System.Type` для типа.  Выражение `typeof` принимает следующую форму:  
  
```  
System.Type type = typeof(int);  
```  
  
## Заметки  
 Для получения типа выражения во время выполнения можно воспользоваться методом платформы .NET <xref:System.Object.GetType%2A>, как показано в следующем примере:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Оператор `typeof` перегрузить нельзя.  
  
 Оператор `typeof` может также использоваться с открытыми универсальными типами.  Типы с более чем одним параметром типа должны иметь соответствующее количество запятых в спецификации.  В следующем примере показано, как определить, является ли тип возвращаемого значения универсальным <xref:System.Collections.Generic.IEnumerable%601>.  Предполагается, что метод является экземпляром типа MethodInfo:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## Пример  
 [!CODE [csrefKeywordsOperator#12](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#12)]  
  
## Пример  
 В этом примере для определения типа, используемого для размещения результата численного вычисления, применен метод <xref:System.Object.GetType%2A>.  Тип зависит от требований, предъявляемых для хранения получаемого в результате числа.  
  
 [!CODE [csrefKeywordsOperator#13](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsOperator#13)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 <xref:System.Type?displayProperty=fullName>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)