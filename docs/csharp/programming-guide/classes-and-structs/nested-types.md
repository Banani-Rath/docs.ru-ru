---
title: "Вложенные типы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "вложенные типы [C#]"
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Вложенные типы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип, определенный внутри [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), называется вложенным типом.  Пример:  
  
 [!CODE [csProgGuideObjects#68](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#68)]  
  
 Независимо от того, являются ли внешние типы классом или структурой, вложенные типы по умолчанию являются [private](../../../csharp/language-reference/keywords/private.md), но могут быть также [public](../../../csharp/language-reference/keywords/public.md), protected internal, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md).  В предыдущем примере тип `Nested` недоступен для внешних типов, но он может быть являться открытым \(public\):  
  
 [!CODE [csProgGuideObjects#69](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#69)]  
  
 Вложенный тип может получить доступ к вмещающему типу, а внутренний тип — к внешнему.  Чтобы получить доступ к вмещающему типу, передайте его в качестве конструктора во вложенный тип.  Пример:  
  
 [!CODE [csProgGuideObjects#70](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#70)]  
  
 Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу.  Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.  
  
 В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`.  Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:  
  
 [!CODE [csProgGuideObjects#71](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#71)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)