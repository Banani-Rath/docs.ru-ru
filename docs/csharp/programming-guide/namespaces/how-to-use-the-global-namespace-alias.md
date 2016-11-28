---
title: "Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#) | Microsoft Docs"
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
  - "псевдонимы [C#]"
  - "глобальное пространство имен [C#]"
  - "пространства имен [C#], квалификатор глобального пространства имен"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возможность доступа к члену в глобальном [пространстве имен](../../../csharp/language-reference/keywords/namespace.md) полезна, когда этот член может быть скрыт другой сущностью с таким же именем.  
  
 Например, в следующем коде `Console` разрешается в тип `TestApp.Console` вместо типа `Console` в пространстве имен <xref:System>.  
  
 [!CODE [csProgGuide#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#1)]  
  
 [!CODE [csProgGuideNamespaces#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#1)]  
  
 При использовании `System.Console` все равно возникает ошибка, так как пространство имен `System` скрыто классом `TestApp.System`:  
  
 [!CODE [csProgGuideNamespaces#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#2)]  
  
 Однако данную ошибку можно устранить следующим образом, используя `global::System.Console`:  
  
 [!CODE [csProgGuideNamespaces#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#3)]  
  
 Когда левый идентификатор имеет значение `global`, поиск правого идентификатора начинается в глобальном пространстве имен.  Например, следующее объявление ссылается на `TestApp` как на член глобального пространства.  
  
 [!CODE [csProgGuideNamespaces#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#4)]  
  
 Очевидно, что необходимость в создании пространства имен `System` отсутствует, а вероятность повстречать код, где это сделано, очень мала.  Однако в более крупных проектах существует большая вероятность встретить ту или иную форму дублирования пространства имен.  В такой ситуации квалификатор глобального пространства имен является гарантирует возможность задания корневого пространства имен.  
  
## Пример  
 В данном примере пространство имен `System` используется для включения класса `TestClass`, поэтому для создания ссылки на класс `System.Console`, скрытый пространством имен `System`, необходимо использовать `global::System.Console`.  Кроме того, псевдоним `colAlias` используется для создания ссылки на пространство имен `System.Collections`; таким образом при создании экземпляра <xref:System.Collections.Hashtable?displayProperty=fullName> вместо пространства имен использовался этот псевдоним.  
  
 [!CODE [csProgGuideNamespaces#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#5)]  
  
  **А 1**  
**В 2**  
**С 3**   
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Оператор .](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)