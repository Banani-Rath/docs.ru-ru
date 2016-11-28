---
title: "В типе &lt;имяТипа&gt; отсутствуют конструкторы | Microsoft Docs"
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
  - "bc30251"
  - "vbc30251"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30251"
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# В типе &lt;имяТипа&gt; отсутствуют конструкторы
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип не поддерживает вызов в `Sub New()`.  Одной из возможных причин является повреждение компилятора или двоичного файла.  
  
 **Идентификатор ошибки:** BC30251  
  
### Исправление ошибки  
  
1.  Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.  
  
2.  Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.  
  
3.  Если устранить ошибку не удается, переустановите компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
4.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## См. также  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Обращайтесь к нам](/visual-studio/ide/talk-to-us)