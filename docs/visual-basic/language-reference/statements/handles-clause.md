---
title: "Предложение Handles (Visual Basic) | Microsoft Docs"
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
  - "Handles"
  - "vb.Handles"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Handles - ключевое слово"
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Предложение Handles (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Заявляет, что процедура обрабатывает указанное событие.  
  
## Синтаксис  
  
```  
  
proceduredeclaration Handles eventlist  
```  
  
## Части  
 `proceduredeclaration`  
 Объявление процедуры `Sub` для процедуры, которая будет обрабатывать событие.  
  
 `eventlist`  
 Список событий, обрабатываемых `proceduredeclaration`, с разделителями\-запятыми.  События должны вызываться базовым классом для текущего класса либо объектом, объявленным с помощью ключевого слова `WithEvents`.  
  
## Заметки  
 Используйте ключевое слово `Handles` в конце объявления процедуры, чтобы она обрабатывала события, вызванные переменной объекта, которая объявлена с помощью ключевого слова `WithEvents`.  Ключевое слово `Handles` может также использоваться в производном классе для обработки событий из базового класса.  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.  Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.  Оператор `AddHandler` подключает процедуры к событиям во время выполнения.  Дополнительные сведения см. в разделе [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Для пользовательских событий приложение вызывает метод доступа `AddHandler` события во время добавления процедуры в качестве обработчика событий.  Дополнительные сведения о пользовательских событиях см. в разделе [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Пример  
 [!CODE [VbVbalrEvents#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#2)]  
  
 В следующем примере показано, как производный класс может использовать оператор `Handles` для обработки события из базового класса.  
  
 [!CODE [VbVbalrEvents#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#3)]  
  
## Пример  
 В следующем примере приведены два обработчика событий кнопки для проекта **Приложение WPF**.  
  
 [!CODE [VbVbalrEvents#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#41)]  
  
## Пример  
 Следующий пример эквивалентен предыдущему примеру:  `eventlist` в предложении `Handles` содержит события для обеих кнопок.  
  
 [!CODE [VbVbalrEvents#42](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#42)]  
  
## См. также  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)