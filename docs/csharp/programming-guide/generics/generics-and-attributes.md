---
title: "Универсальные шаблоны и атрибуты (Руководство по программированию в C#) | Microsoft Docs"
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
  - "атрибуты [C#], с универсальными"
  - "универсальные шаблоны [C#], атрибуты"
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Универсальные шаблоны и атрибуты (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Атрибуты применяться к универсальным типам таким же образом, как и к нестандартным типам.  Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Настраиваемым атрибутам разрешено ссылаться только на открытые универсальные типы \(универсальные типы, для которых не предоставлены аргументы типа\) и закрытые сконструированные универсальные типы \(которые предоставляют аргументы для всех параметров типа\).  
  
 В следующем примере используется этот настраиваемый атрибут:  
  
 [!CODE [csProgGuideGenerics#48](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#48)]  
  
 Атрибут может ссылаться на открытый универсальный тип:  
  
 [!CODE [csProgGuideGenerics#49](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#49)]  
  
 Укажите несколько параметров типа, используя соответствующее количество запятых.  В данном примере у `GenericClass2` имеется два параметра:  
  
 [!CODE [csProgGuideGenerics#50](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#50)]  
  
 Атрибут может ссылаться на закрытый сконструированный универсальный тип:  
  
 [!CODE [csProgGuideGenerics#51](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#51)]  
  
 Атрибут, ссылающийся на параметр универсального типа, приведет к ошибке времени компиляции:  
  
 [!CODE [csProgGuideGenerics#52](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#52)]  
  
 Универсальный тип не может наследовать от <xref:System.Attribute>:  
  
 [!CODE [csProgGuideGenerics#53](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#53)]  
  
 Для получения информации об универсальном типе или параметре типа во время выполнения можно использовать методы <xref:System.Reflection>.  Дополнительные сведения см. в разделе [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Атрибуты](../Topic/Extending%20Metadata%20Using%20Attributes.md)