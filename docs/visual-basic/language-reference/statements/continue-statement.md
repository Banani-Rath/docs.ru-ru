---
title: "Оператор Continue (Visual Basic) | Microsoft Docs"
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
  - "vb.continue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Continue - оператор [Visual Basic]"
  - "циклы, передача до следующей итерации"
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Continue (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Передает управление непосредственно следующей итерации цикла.  
  
## Синтаксис  
  
```  
Continue { Do | For | While }  
```  
  
## Заметки  
 Можно перейти из очередной итерации цикла `Do`, `For` или `While` к следующей итерации этого цикла.  Управление немедленно передается проверке условия цикла, что эквивалентно передаче оператору `For` или `While`, либо оператору `Do` или `Loop`, который содержит предложение `Until` или `While`.  
  
 `Continue` можно использовать в любом месте в цикле, в котором возможна передача.  Правила разрешения передачи управления такие же, как для [Оператор GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Например, если цикл полностью содержится внутри блока `Try`, `Catch` или `Finally`, можно использовать `Continue` для передачи вне цикла.  Если, с другой стороны, структура блока `Try`...`End Try` находится внутри цикла, то нельзя использовать `Continue` для передачи управления из блока `Finally`, а можно использовать для передачи из блока `Try` или `Catch`, только если передача полностью вне структуры `Try`... `End Try`.  
  
 Если есть вложенные циклы одного типа, например, цикл `Do` в цикле `Do`, то инструкция `Continue Do` осуществляет переход к следующей итерации самого внутреннего цикла `Do`, в котором она содержится.  Чтобы перейти к следующей итерации включающего цикла того же, нельзя использовать `Continue`.  
  
 Если имеются вложенные циклы различного типа, например, цикл `Do` в цикле `For`, то можно перейти к следующей итерации любого цикла с помощью `Continue Do` или `Continue For`.  
  
## Пример  
 В следующем примере используется инструкция `Continue While`, чтобы перейти к следующему столбцу массива, если делитель равен нулю.  `Continue While` находится внутри цикла `For`.  Он передает управление инструкции `While col < lastcol`, которая является следующей итерацией внутреннего цикла `While`, который содержит цикл `For`.  
  
 [!CODE [VbVbalrStatements#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#14)]  
  
## См. также  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)