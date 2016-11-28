---
title: "Свойства оси XML не поддерживают позднее связывание | Microsoft Docs"
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
  - "bc31168"
  - "vbc31168"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31168"
ms.assetid: 45707363-55e4-4151-892d-d8729106355b
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Свойства оси XML не поддерживают позднее связывание
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Свойство XML axis ссылается на нетипизированный объект.  
  
 **Идентификатор ошибки:** BC31168  
  
### Чтобы исправить эту ошибку  
  
-   Убедитесь, что объект является типобезопасным <xref:System.Xml.Linq.XElement> перед ссылкой на свойство XML axis.  
  
## См. также  
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)