---
title: "Пространства имен (Руководство по программированию в C#) | Microsoft Docs"
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
  - "C# - язык, пространства имен"
  - "пространства имен [C#]"
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Пространства имен (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В программировании на C\# пространства имен используются с полной нагрузкой по двум направлениям.  Во\-первых, платформа .NET Framework использует пространства имен для организации большинства классов. Это выполняется следующим образом.  
  
 [!CODE [csProgGuide#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#22)]  
  
 `System` — это пространство имен, а `Console` — класс в нем.  Использование ключевого слова `using` может отменить необходимость полного имени, как показано в следующем примере.  
  
 [!CODE [csProgGuide#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#1)]  
  
 [!CODE [csProgGuide#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#25)]  
  
 Дополнительные сведения см. в разделе [Директива using](../../../csharp/language-reference/keywords/using-directive.md).  
  
 Во\-вторых, объявление собственного пространства имен поможет в управлении областью действия имен классов и методов в крупных программных проектах.  Для объявления пространства имен воспользуйтесь ключевым словом [namespace](../../../csharp/language-reference/keywords/namespace.md), как показано в следующем примере.  
  
 [!CODE [csProgGuideNamespaces#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#6)]  
  
## Общие сведения о пространствах имен  
 Пространства имен имеют следующие свойства.  
  
-   Организация крупных проектов по созданию кода.  
  
-   Для их разделения используются оператор `.`.  
  
-   `using directive` исключает требование на указание имени пространства имен для каждого класса.  
  
-   Пространство имен `global` является корневым пространством имен: `global::System` всегда будет ссылаться на пространство имен платформы .NET Framework `System`.  
  
## Связанные разделы  
 Дополнительные сведения о пространствах имен см. в следующих разделах:  
  
-   [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Практическое руководство. Использование пространства имен "My"](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Директива using](../../../csharp/language-reference/keywords/using-directive.md)   
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [Оператор .](../../../csharp/language-reference/operators/member-access-operator.md)