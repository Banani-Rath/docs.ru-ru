---
title: "Выполнение оператора Resume без ошибки | Microsoft Docs"
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
  - "vbrID20"
dev_langs: 
  - "VB"
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Выполнение оператора Resume без ошибки
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор`Resume` обнаружен вне кода обработки ошибки, или код выполнил переход к обработчику ошибок, хотя ошибок не было.  
  
### Чтобы исправить эту ошибку  
  
1.  Переместите оператор `Resume`в обработчик ошибок или удалите его.  
  
2.  Переход к меткам через несколько процедур невозможен, поэтому следует выполнить поиск метки, обозначающей обработчик ошибок, в данной процедуре.  Если обнаружена повторяющаяся метка, являющаяся конечным объектом оператора `GoTo`, который входит в оператор `On Error GoTo`, измените метку строки таким образом, чтобы она соответствовала конечному объекту.  
  
## См. также  
 [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)