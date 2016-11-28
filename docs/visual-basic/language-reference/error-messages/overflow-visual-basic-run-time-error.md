---
title: "Переполнение (Ошибка во время выполнения Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrERRID_Overflow"
dev_langs: 
  - "VB"
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Переполнение (Ошибка во время выполнения Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переполнение является результатом присваивания, которое нарушает ограничения присваиваемого результата.  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что результаты назначений, вычислений или преобразований типов данных входят в диапазон переменных, разрешенный для данного типа значения, и при необходимости назначьте значение переменной, тип которой позволяет использовать больший диапазон значений.  
  
2.  Убедитесь, что значения, присваиваемые свойству, входят в диапазон свойства.  
  
3.  Убедитесь, что используемые в вычислениях числа, которые затем преобразуются в целые числа, не дают результатов, превышающих целые числа.  
  
## См. также  
 <xref:System.Int32.MaxValue?displayProperty=fullName>   
 <xref:System.Double.MaxValue?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)