---
title: "Оператор Erase (Visual Basic) | Microsoft Docs"
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
  - "vb.Erase"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Erase - ключевое слово"
  - "Erase - оператор"
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Erase (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для удаления переменных типа массив и высвобождения памяти, отведенной под их элементы.  
  
## Синтаксис  
  
```  
Erase arraylist  
```  
  
## Части  
 `arraylist`  
 Обязательный.  Список удаляемых переменных типа массив.  Несколько переменных разделяются запятыми.  
  
## Заметки  
 Оператор `Erase` может применяться только на уровне процедур.  Это означает, что удалять переменные типа массив можно внутри процедуры, но не на уровне класса или модуля.  
  
 Оператор `Erase` эквивалентен по своему действию присваиванию значения `Nothing` каждой переменной массива.  
  
## Пример  
 В этом примере показано использование оператора `Erase` для удаления двух массивов и высвобождения использовавшейся ими памяти \(1000 и 100 элементов, соответственно\).  Затем с помощью оператора `ReDim` трехмерному массиву присваивается новый экземпляр массива.  
  
 [!CODE [VbVbalrStatements#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#19)]  
  
## См. также  
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)