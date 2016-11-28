---
title: "Практическое руководство. Передача процедур другой процедуре в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf - оператор"
  - "делегаты [Visual Basic], процедуры передачи"
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Передача процедур другой процедуре в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере показано использование делегатов для передачи процедуры другой процедуры.  
  
 Делегат — это тип, который можно использовать как любой другой тип в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Оператор `AddressOf` возвращает объект делегата при применении к имени процедуры.  
  
 В этом примере показана процедура с параметром делегатом, который может принимать ссылку на другую процедуру, полученную с помощью оператора `AddressOf`.  
  
### Создание делегата и согласование процедур  
  
1.  Создайте делегата с именем `MathOperator`.  
  
     [!CODE [VbVbalrDelegates#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#1)]  
  
2.  Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые совпадают с `MathOperator`, то есть сигнатуры совпадают.  
  
     [!CODE [VbVbalrDelegates#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#2)]  
  
3.  Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.  
  
     [!CODE [VbVbalrDelegates#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#3)]  
  
4.  Создайте процедуру с именем `DelegateTest`, которая принимает делегат в качестве параметра.  
  
     Эта процедура может принимать ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуре соответствуют сигнатура `MathOperator`.  
  
     [!CODE [VbVbalrDelegates#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#4)]  
  
5.  Создайте процедуру с именем `Test`, которая сначала вызывает `DelegateTest` с делегатом для `AddNumbers` в качестве параметра и затем снова с делегатом для `SubtractNumbers` в качестве параметра.  
  
     [!CODE [VbVbalrDelegates#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#5)]  
  
     Когда вызывается `Test`, то сначала он отображает результат действия `AddNumbers` на значения `5` и `3`, и этот результат равен 8.  Затем отображается результат действия `SubtractNumbers` на `9` и `3`, который равен 6.  
  
## См. также  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Практическое руководство. Вызов метода делегата](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)