---
title: "Универсальные методы и массивы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], универсальные шаблоны"
  - "универсальные шаблоны [C#], массивы"
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Универсальные методы и массивы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В C\# версии 2.0 и более поздней версии одномерные массивы с нижней границей, равной нулю, автоматически реализуют <xref:System.Collections.Generic.IList%601>.  Это позволяет создавать универсальные методы, которые могут использовать тот же код для итерации массивов и других типов коллекции.  Данный метод особенно полезен для чтения данных в коллекциях.  Интерфейс <xref:System.Collections.Generic.IList%601> нельзя использовать для добавления или удаления элементов из массива.  При попытке вызова метода <xref:System.Collections.Generic.IList%601>, такого как <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, в массиве в данном контексте, возникнет исключение.  
  
 В следующем примере кода показано, как отдельный универсальный метод, принимающий входной параметр <xref:System.Collections.Generic.IList%601>, может выполнять итерацию списка и массива – в данном случае массива целых чисел.  
  
 [!CODE [csProgGuideGenerics#35](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#35)]  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)